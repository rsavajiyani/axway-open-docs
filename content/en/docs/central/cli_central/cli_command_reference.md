---
title: AMPLIFY Central CLI Command Index
linkTitle: AMPLIFY Central CLI Command Index
weight: 130
date: 2021-01-13T00:00:00.000Z
description: Learn about the different AMPLIFY Central CLI commands you can use
---

## **get**

List one or more resources.

Prints a table of the most important information about the specified resources.

If the desired resource type is scoped you will need to specify the scope name by providing `-s, --scope <name>` flag.

You can query for more than one resource if using comma-separated resources in the command (see the examples).

Querying for multiple resources will display multiple result tables, one result table for each resource you fetch.

To see the list of all available resources from AMPLIFY Central, run `amplify central get`

### Usage

`amplify central get [options] [<args...>]`

`amplify central get <Resource>` Get a list of the resources

`amplify central get <Resource1>,<Resource2>,...,<ResourceN>` Get a list of multiple resources

`amplify central get <Resource> <Name> -s/--scope <Scope Name>` Get a specific resource by name

### Get Options

`--client-id=<value>` Override your DevOps account's client ID

`-o,--output=<value>` Additional output formats. One of: yaml | json

`-s,--scope=<name>` Scope name for scoped resources.

### Get Arguments

`args...` Command arguments, run `amplify central get` to see the examples

### Get Examples

```
# get all environments
amplify central get envs
# get all environments in yaml format
amplify central get environments -o yaml
# get environment by Resource/Common name in json format
amplify central get env myenv -o json
# get all webhooks
amplify central get webhooks
# get all webhooks by Short Name
amplify central get webh
# get all webhooks and apiservices by Short Name
amplify central get webh,apis
# get all environments and api services
amplify central get envs,apisvc
# get environment and apiservice which matches a Resource/Common Name in a specified scope(scope is required ater -s flag) in json format
amplify central get env,apisvc commonname -s env1 -o json
```

For more examples, please see the [Create and fetch Resources via the AMPLIFY Central CLI](https://docs.axway.com/bundle/axway-open-docs/page/docs/central/cli_central/cli_create_fetch_resources/index.html) page.
- - -

## **create**

Create one or more resources from a YAML | JSON file or Stdin.

### Create Usage

`amplify central create <command> [options]`

### Create Commands

`environment` Create an environment with the specified name

`service-account` Create a service account

### Create Options

`--client-id=<value>` Override your DevOps account's client ID

`-f,--file=<path>` Filename to use to create the resource

`-o,--output=<value>` Additional output formats. One of: YAML | JSON

`--region=<value>` Override your region config

#### **create: multiple resources from a file**

Usage: `amplify central create -f <path_to_file>`

#### **create: specific resource by name**

**_Note: Only environments are currently available for this command._**

Usage: `amplify central create environment [options] <name>`
Create an environment with the specified name

#### Environment Arguments

`name`          Name of new environment

### Create Examples

```bash
# create new environment with "newenv" name
amplify central create env newenv
# create new environment with "newenv" name and output result in yaml
amplify central create environment newenv -o yaml
# create multiple resources from file
amplify central create -f ./some/folder/resources.yaml
# create a service account(DOSA)
amplify central create service-account
```

- - -

## **apply**

Update resources from a file.

The resource name must be specified in the file. This resource will be created if it doesn't exist yet.

### Apply Usage

`amplify central apply [options]`

### Apply Options

  `--client-id=<value>`   Override your DevOps account's client ID

  `-f,--file=<path>`      Filename to use to create or update the resources. One of: yaml | json

  `-o,--output=<value>`  Additional output formats. One of: YAML | JSON

### Apply Examples

```bash
# create multiple resources from file
amplify central apply -f ./some/folder/resources.yaml
# create multiple resources from file and output results in YAML format
amplify central apply -f ./some/folder/resources.json -o yaml
```

- - -

## **delete**

Delete resources by type name or file name.

When deleting the single resource by its name if the desired resource type is scoped you will need to specify the scope
name by providing `-s, --scope <name>` flag.

To see the list of all available resources on the server run `amplify central delete`.

### Delete Usage

`amplify central delete [options] [<args...>]`

### Delete Options

`--client-id=<value>`   Override your DevOps account's client ID

`-f,--file=<path>`      Filename to use to delete the resource

`-s,--scope=<name>`     Scope name for scoped resources.

`--wait`                Wait for the resources to be completely deleted

### Delete Arguments

  `args...`               Command arguments, run `amplify central delete` to see the examples

### Delete Examples

```bash
# delete environment by name
amplify central delete environment newenv
# delete api service by name (a scoped resource)
amplify central delete apisvc someapisvc -s newenv
# delete all resources specified in the file
amplify central delete -f ./some/folder/resources.yaml
```

- - -

## **edit**

Edit and update resources by using the default editor

### Edit Usage

`amplify central edit <command> [options]`

### Edit Commands

  `environment`   Edit an environment with the specified name.

### Edit Options

  `--client-id=<value>`   Override your DevOps account's client ID

  `-o,--output=<value>`   Additional output formats. One of: yaml|json

#### **edit: resource by name**

Edit an environment with the specified name.

_Using "environment" as an example._

Usage:

`amplify central edit environment [options] <name>`

Environment Arguments:

  `name`          Name of the environment

### Edit Examples

```bash
# delete environment by name
amplify central edit environment newenv
```

- - -

## **install**

Install additional platform resources

### Install Usage

`amplify central install <command> [options] [<args...>]`

### Install Commands

  `agents`                Install v7 / AWS / kubernetes agent.

### Install Arguments

  `args...`               Command arguments, run `amplify central install` to see the examples

### Install Options

`--client-id=<value>`   Override your DevOps account's client ID

`--region=<value>`      Override your region config

#### **install: agents configuration**

Install API Gateway v7 / Amazon API Gateway / Kubernetes agents

Usage:

`amplify central install agents [options]`

Install Options:

  `--client-id=<value>`   Override your DevOps account's client ID

`--region=<value>`      Override your region config

#### Install Examples

```bash
# install agent configuration in interactive mode
amplify central install agents
```
