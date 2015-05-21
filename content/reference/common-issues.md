+++
title = "Common Issues & Questions"
description = "On this page you can find some answers to common issues and questions around our service."
date = "2015-05-21"
type = "page"
weight = 100
+++

# Common Issues & Questions

Question | Answer
-------- | ------
Can I use my own domain? | Yes, just create a CNAME to loadbalancer.giantswarm.io and then use your domain in the [application configuration](http://docs.giantswarm.io/reference/swarm-json/#domains).
How can I create backups or snapshots from volumes? | We currently don't provide this as a service. You have to take care of it yourself. You can use S3 or other storage solutions. For an example check out our guide for [MySQL with Backups](http://docs.giantswarm.io/guides/mysql-backup/). 
Can I run a database? | Yes, for most databases there are ready built containers in the [Docker Hub](https://registry.hub.docker.com/). If you can't find one for your database of choice, you should be able to easily build one. And don't forget to use [volumes](http://docs.giantswarm.io/reference/swarm-json/#volumes).
Can I run a database cluster? | In general (and on our dedicated clusters): Yes. In many cases on our shared cluster: No, as they usually need somekind of multicast networking or DNS.
How do I make components talk to each other? | You can use [dependencies](http://docs.giantswarm.io/reference/swarm-json/#dependencies), which work like links in Docker Compose.
How can I provide environment variables for the containers/components? | Use the "env" key in your [application configuration](http://docs.giantswarm.io/reference/swarm-json/#env) or a [swarm-vars.json](http://docs.giantswarm.io/reference/cli/create/#passing-variables-in-a-file)
Can I use TLS/HTTPS/SSL? | Not yet, but we're working on it.
How do I apply changes to the configuration of my application? | Currently, you can't update your application. You will have to delete and re-create the application, which sounds drastic, but actually won't do any harm, as long as you have a stateless application. If you just updated an image, you can use [`swarm update`](http://docs.giantswarm.io/reference/cli/update/) to update the component that uses that image.
Does the ordering of services and components have an effect? | No, but dependencies do have an effect on startup order. The dependency is always started before the dependent.
What happens, if I create cyclic dependencies between components? | There will be an error. Currently we don't support those kind of dependencies in our application configuration.
Why don't you provide a 32 bit version of the swarm CLI? | There is no 32bit version of Docker, and having swarm without Docker on a system didn't appear to be a very common use-case.
Is there a Windows version of the swarm CLI? | Currently no, but you can use a Vagrant (or similar) VM with a Linux (e.g. ubuntu/trusty64) in it, to run our CLI in.
Can I use a third party private registry with Giant Swarm? | No, currently you can only use our own [private registry](http://docs.giantswarm.io/reference/registry/) or any public registry like the Docker Hub for example.
Can I use --volumes-from? | Currently not, but we're working on it.
How can I prevent automated deletion of my application in Alpha? | Just add a custom domain entry that is not *.gigantic.io to your [application configuration](http://docs.giantswarm.io/reference/swarm-json/#domains).
How can I run a container periodically? | Currently, this is not possible directly, but there's a workaround: Create a dedicated container/component running a script in an endless loop with a pause between job executions (we can provide example code). If that component is in it's own service, it can be stopped via the CLI or API so it doesn't have to run idle and use resources, and then be started again at the required times using some outside mechanism. As a side note, manual triggering of job execution is possible using [`swarm exec`](http://docs.giantswarm.io/reference/cli/exec/).

Can't find the answer to your question here? Send us an email to [support@giantswarm.io](mailto:support@giantswarm.io) or hop on [Gitter](https://gitter.im/giantswarm/users) and chat with us. Of course [pull requests](https://github.com/giantswarm/docs-content) are also welcome.