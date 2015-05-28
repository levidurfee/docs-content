+++
title = "Getting basic information"
description = "Reference page for the `swarm info` command, which allows you to get some basic information on your login and environment status."
date = "2015-01-29"
type = "page"
categories = ["Reference", "Swarm CLI Commands"]
tags = ["swarm info"]
weight = 80
+++

# `swarm info`: Get Basic Information

The `swarm info` command provides information about a Giant Swarm account, including cluster status, CLI verson, logged in user and the current enviroment.

## Command syntax

The `swarm info` comand is called without any arguments by doing:

```nohighlight
swarm info
```

#### Example with Response

```nohighlight
$ swarm info
Cluster status:      reachable
Swarm CLI version:   0.17.0
Logged in as user:   bant
Current environment: bant/dev
```

### Response Explained

* __Cluster status__: The general platform health, normally `reachable`.
* __Logged in as user__: The current logged in username. 
* __Current environment__: The current working environment.

*Hint: If you are only interested in the current user name, you can use the [`swarm user`](/reference/cli/user/) command. The same is true of the current environment, which can be retrieved using [`swarm env`](/reference/cli/env/).*

## Further reading

* [Environments](/reference/cli/env/)
* [Organizations](/reference/cli/org/)
