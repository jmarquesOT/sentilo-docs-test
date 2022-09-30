Site customization
------------------

Environment info band
~~~~~~~~~~~~~~~~~~~~~

It is now possible to indicate the environment in which the catalog 
application works by of an informative band.

|catalog_env_band.png|

|delete_error.png|

If this feature is enabled, the band will be displayed throughout 
the catalog application.

This property is very useful when we want to easily highlight the 
environment in which we are working (for example, to differentiate 
between development and production environments).

In order to activate it, we must give the value that we want to 
show to the following property of the configuration file:

::

	#ribbon text
	sentilo.catalog.ribbon.text=DOCKER
	
If you don't want to use this property, just leave it blank or 
comment out the line.