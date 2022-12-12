Cluster mode
============

Introduction
------------

Since version 2.0, Sentilo offers the possibility of configuring the instance 
to work in **cluster mode**, thus favoring *high availability (HA)*.

Since this mode substantially improves response times and overall performance 
of all platform components, *it is highly recommended to configure production 
environments using this method*.

Sentilo will improve its performance thanks to the particularity of the Redis 
Cluster mode, which improves the response times of the stored data, as well as 
a great improvement in its transmission, partly thanks to the use of *Redis streams*, 
also introduced in the version 2.0.


Requirements
------------

To activate the cluster mode or high availability of Sentilo it is necessary to 
modify a specific parameterization that we will discuss below.

In addition, the use of the **Redis cluster mode is mandatory**.

If you want to have several instances of the API Server and/or the Catalog, 
you must have a *web balancer*, such as **NGINX**, to be able to balance the 
load of the servers


Configuration
-------------

Once we have all the requirements ready (especially the *Redis Cluster mode*), 
we must make the following modifications in the Sentilo configuration:

- File **sentilo.conf**: configure the parameters associated with the *Redis cluster* 
  (:literal:`sentilo.redis.cluster.nodes`, see it at `Default settings <./api_docs/setup.html#default-settings>`__)
- For every Sentilo artifact *startup scripts*: add the *JVM param* :literal:`-Dspring.profiles.active=cluster*`.

Once this is done, we can start our instance in high availability cluster mode normally.