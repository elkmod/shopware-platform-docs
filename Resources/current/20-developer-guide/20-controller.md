# 20-controller

## Controllers guide

For a plugin to be useful, it generally needs to offer an interface to the outside world, this is what controllers and routes are for. If you've already used Symfony or other web frameworks, this will sound familiar to you. Since Shopware 6 was built as a Symfony application, there are almost no differences between how controllers are created and used in Symfony and how this is done in Shopware.

In case you're not familiar with the wording here - A route is essentially an externally accessible controller method. So for a controller to be of any use, you need to define routes via which its methods can be accessed. Read on, to find out how this can be done with Shopware.

### Adding controllers to a plugin

Since Shopware plugins are essentially [Symfony bundles](https://symfony.com/doc/current/bundles.html#creating-a-bundle) , the [configuration pattern](https://symfony.com/doc/current/configuration.html) of Symfony applies. To make Shopware aware of a new controller, you need to place a config file in the `Resources/config` directory of your plugin. This config file has to have the string `routes` [in its filename or path](../50-how-to/020-api-controller.md#loading-the-controllers-via-routesxml) and can be written in `yaml`, `xml` or `php`.

```text
./
+-- AcmeExamplePlugin/
    +-- composer.json
    +-- Resources/
        +-- config/
            +-- routes.xml
    +-- src/
        +-- AcmeExamplePlugin.php
```

When given the following `routes.xml`, Shopware will search for classes with a [`@Route`](https://symfony.com/doc/current/bundles/SensioFrameworkExtraBundle/annotations/routing.html#route-annotation) annotation in the `Controller` directory and register them accordingly:

```markup
<?xml version="1.0" encoding="UTF-8" ?>

<routes xmlns="http://symfony.com/schema/routing"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://symfony.com/schema/routing http://symfony.com/schema/routing/routing-1.0.xsd">

    <import resource="../../src/Controller" type="annotation" />
</routes>
```

Besides the default `@Route` annotation, there's a `@RouteScope` annotation in Shopware. This annotation is used, to define which domain a route is part of and **needs to be set for every route**:

```php
/**
 * @RouteScope(scopes={"api"})
 */
class MyController extends AbstractController
{
    /**
     * @Route("/api/v{version}/acme/do-something", name="api.action.acme.do-something", methods={"POST"})
     */
    public function doSomething(Request $request, Context $context): JsonResponse
    {
        return new JsonResponse([
            // ...
        ]);
    }
}
```

The `RouteScope` may also be set per route:

```php
/**
 * @RouteScope(scopes={"api"})
 * @Route("/api/v{version}/acme/do-something", name="api.action.acme.do-something", methods={"POST"})
 */
```

A `Route` can have multiple `RouteScopes`:

```php
/**
 * @RouteScope(scopes={"storefront", "custom-scope"})
 * @Route("/api/v{version}/acme/fetch-a-thing", name="api.action.acme.fetch-a-thing", methods={"GET"})
 */
```

## Controller differences

Shopware does not offer one API, but multiple purpose-built ones for different use-cases. Creating and registering controllers for these APIs is done the same way for all of them, but there are some minor differences in configuration or how a controller in a certain domain should be integrated and used - these are covered in the following sections.

### Admin API Controller

An [admin API controller](../50-how-to/020-api-controller.md) can be registered like described above, the only thing to remember apart from that is to use the corresponding `RouteScope`:

```php
/**
 * @RouteScope(scopes={"api"})
 */
class AcmeCustomAdministrationController extends AbstractController
{
    // Define your routes here
}
```

### Store API / Storefront controller

Since Shopware v6.2, there's a new concept we suggest for creating storefront controllers which ensures, that the storefront functionality and the functionality offered via the store API do not drift apart. This is done by using the store API controllers essentially as a backend for the storefront controllers. You can read more about this concept `here` .

### Storefront controller

A [storefront controller](../50-how-to/580-custom-storefront-controller.md) can be registered like described [above](20-controller.md#adding-controllers-to-a-plugin) . Apart from that, use the `storefront` `RouteScope` and extend from the `StorefrontController` instead of the `AbstractController`:

```php
/**
 * @RouteScope(scopes={"storefront"})
 */
class AcmeCustomStorefrontController extends StorefrontController
{
    // Define your routes here
}
```

This controller can now use a [`PageLoader`](../60-references-internals/30-storefront/10-composite-data-loading.md) or similar service to load a page:

```php
public function doSomething(Request $request, Context $context)
{
    $page = $this->pageLoader->load(
        $request,
        $context
    );

    return $this->renderStorefront(
        '@AcmeExamplePlugin/storefront/page/example-template.html.twig',
        [
            'page' => $page
        ]   
    )
}
```

### Store API controller \(route\)

The `PageLoader`s used by the storefront controllers in turn can call Store API controllers to fetch the data necessary for rendering the page. A Store API controller needs to have the `store-api` `RouteScope` and should only care about one thing, for example, returning a product or an address. This is an example of a Store API controller:

```php
/**
 * @RouteScope(scopes={"store-api"})
 */
class AcmeExampleRoute
{
    /**
     * @Route("/store-api/v{version}/acme-example/{entityId}", methods={"POST"})
     * @OA\Post(...)
     */
    public function load(string $entityId, Request $request, SalesChannelContext $salesChannelContext): AcmeExampleResponse
    {
        return new AcmeExampleResponse(
            $this->entityRepository->search(new Criteria([$entityId]), $salesChannelContext)
        );
    }
}
```

To learn more about Store API controllers, have a look at the [Store API](../45-store-api-guide/__categoryinfo.md) documentation.

