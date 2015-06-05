+++
title = "Starting an application or service"
description = "This is the reference page for the 'swarm start' command, which allows you to start an application or service."
date = "2014-12-11"
type = "page"
categories = ["Reference", "Swarm CLI Commands"]
tags = ["swarm start"]
weight = 50
+++

# `swarm start`: Start an Application or Service
The `swarm start` command is used to start an application or a service inside an application after it has been created using the [`swarm create`](/reference/cli/create/) command.

The `swarm up` command is an alias for the combined use of `swarm create` and `swarm start`, which allows the CLI to block and wait for the application to be created, started and achieves running state.

*Note: When an application is started, it will be located in the same organization and environment being used by the `swarm` client.*

## Command Syntax

The `swarm start` command can be called to start an application without any arguments if a valid `swarm.json` file is present in the current working directory:

```nohighlight
swarm start
```

The CLI will normally block and wait for the application to start before it returns control to the shell. The command can also be issued in non-blocking mode using the `-d` or `--detach` flags:

```nohighlight
swarm start --detach
```

The command can also be passed an application name:

```nohighlight
swarm start <app_name>
```

#### Example with Response
```nohighlight
$ swarm start -d helloworld
Starting 'helloworld' in the 'bant/dev' environment...
Application created successfully!
```

## Starting an Service
The `swarm start` command may be used to start a service (a set of components) inside a given application without starting the other services in that application. A single service is started by using the application name, a `/` separator, and the service name by doing:

```nohighlight
swarm start <app_name>/<service_name>
```

#### Example with Response
```nohighlight
$ swarm start -d helloworld/webserver
Starting 'helloworld/webserver' in the 'bant/dev' environment...
Application created successfully!
```

## Further reading

* [Environments](/reference/cli/env/)
* [Application configuration reference (`swarm.json`)](/reference/swarm-json/)
* [Global command line options](/reference/cli/global-options/)
