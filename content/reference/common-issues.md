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
bla | bla
bla | bla
bla | bla
bla | bla
bla | bla
bla | bla
bla | bla

Can't find the answer to your question here? Send us an email to [support@giantswarm.io](mailto:support@giantswarm.io) or hop on [Gitter](https://gitter.im/giantswarm/users) and chat with us. Of course [pull requests](https://github.com/giantswarm/docs-content) are also welcome.