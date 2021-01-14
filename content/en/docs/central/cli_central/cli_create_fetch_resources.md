---
title: Create and fetch resources with the AMPLIFY Central CLI
linkTitle: Create and fetch resources with the AMPLLIFY Central CLI
weight: 120
date: 2021-01-13T00:00:00.000Z
description: Learn about creating and fetching different AMPLIFY Central resources using the CLI
---

## Before You Start

* [Install and authenticate yourself via the AMPLIFY Central CLI.](https://docs.axway.com/bundle/axway-open-docs/page/docs/central/cli_central/cli_install/index.html)
* Familiarize yourself with the [most commonly used AMPLIFY Central CLI commands.](https://docs.axway.com/bundle/axway-open-docs/page/docs/central/cli_central/cli_command_reference/index.html)

## Objectives

* Learn how to create and fetch various types of resources via the AMPLIFY Central CLI's "create" and "get" commands
* Learn about the information the AMPLIFY Central CLI provides when you fetch the resources you've created

## Creating a resource

The AMPLIFY Central CLI supports creating several resources from either a YAML | JSON file or Stdin.

`amplify central create -f <path_to_file>` Create resources defined in a YAML or JSON file.

## Fetching a resource

The AMPLIFY Central CLI lists a table of the most important information about the specified resources. You can query for a singular resource or multiple resources:

`amplify central get <Resource>` Get a list of the resources

`amplify central get <Resource1>,<Resource2>,...,<ResourceN>` Get a list of multiple resources

`amplify central get <Resource> <Name> -s/--scope <Scope Name>` Get a specific resource by name

## Sample Resource Files and Fetch Examples

### Creating and Fetching Consumer Instances

Try creating a Consumer Instance using the [sdkconsumerinstance.json](https://axway-open-docs.netlify.app/samples/central/sdkconsumerinstance.json)

You can then fetch information about your Consumer Instances by running:

`amplify central get consumerinstances` or `amplify central get consumeri`:

```

Resource(s) successfully retrieved

NAME           AGE           TITLE                        RESOURCE KIND            SCOPE KIND   SCOPE NAME
consumerinst1  a month ago   consumerinst1 title          ConsumerInstance         Environment  awsgtw-us-east-2

```

### Creating and Fetching Consumer Subscription Definitions

Try creating a Consumer Subscription Definition using the [apisubscription.json](https://axway-open-docs.netlify.app/samples/central/apisubscription.json)

You can then fetch information about your Consumer Subscription Definitions by running:

`amplify central get consumersubscriptiondefs` or `amplify central get consumersd`:

```

Resource(s) successfully retrieved

NAME             AGE           TITLE                          RESOURCE KIND                          SCOPE KIND   SCOPE NAME
consumersubdef1  a month ago   consumersubdef1 title          ConsumerSubscriptionDefinition         Environment  awsgtw-us-east-2

```

### Creating and Fetching Secrets

Try creating a Secret using the [apisecret.json](https://axway-open-docs.netlify.app/samples/central/apisecret.json).

You can then fetch information about your Secrets by running:

`amplify central get secret` or `amplify central get secrets`:

```
Resource(s) successfully retrieved

NAME        AGE           TITLE                RESOURCE KIND  SCOPE KIND   SCOPE NAME
secretname  4 months ago  secrettitle          Secret         Environment  apigtw-v77
```

### Creating and Fetching Webhooks

Try creating a Webhook using the [apiwebhook.json](https://axway-open-docs.netlify.app/samples/central/apiwebhook.json).

You can then fetch information about your Webhooks by running:

`amplify central get webhooks` or `amplify central get wh` :

```
Resource(s) successfully retrieved

NAME                       AGE           TITLE                             RESOURCE KIND  SCOPE KIND   SCOPE NAME
streams-extension-webhook  a month ago   Streams Extension Webhook         Webhook        Environment  streams-dataplane-integrations
webhook                    6 months ago  Webhook to invoke requestbin.com  Webhook        Environment  cisco-b2bi
msflow                     7 months ago  webhook1 title                    Webhook        Environment  swaggerhub
msflow                     7 months ago  webhook1 title                    Webhook        Environment  azure
subscriptionwebhook        4 months ago  subscriptionwebhook               Webhook        Environment  apigtw-v77
```

## More Sample Resources

You can practice the above pattern of creating and fetching resources using our sample files:

* API Services: [apiservice.json](https://axway-open-docs.netlify.app/samples/central/apiservice.json)

* API Service Instances: [apiendpoint.json](https://axway-open-docs.netlify.app/samples/central/apiendpoint.json)

* API Service Revisions: [apirevisions1.json](https://axway-open-docs.netlify.app/samples/central/apirevisions1.json)

* Environments: [create_environments.json](https://axway-open-docs.netlify.app/samples/central/create_environments.json)

Run `amplify central get` to see the entire list of resources supported by the AMPLIFY Central CLI.