# 610-setup-mail-templates-and-mail-configuration

## Overview

Shopware 6 sends different emails on different purposes. E.g for the registration of a customer or as an order confirmation. To prevent your system from accidently sending mails while it is not live, no mail template is assigned to a sales channel by default.

## Setup

First you need to make sure that you have a correct MAIL_URL set. This has been configured during the setup process and is stored in the .env file in the root directory. Then you need to setup your email address for outgoing mails in the administration \(Settings-&gt;Basic information-&gt;Shop owner email address\). After that the mail template which should be sent have to be assigned to the sales channel. \(Settings-&gt;Email templates-&gt;\_Template_-&gt;edit-&gt;Sales Channels\)

Now your shop is set up to send mails for the given events.

## Change email templates

You can change any Email template in the administration as well. Just go to the Email templates \(Settings-&gt;Email templates-&gt;_Template_-&gt;edit\) and change the content of the templates in the _plain_ and _HTML_ boxes.

