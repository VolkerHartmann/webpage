---
title:  "Installation"
breadcrumbs: /base-repo/installation
layout: default
description: A Generic, General Purpose Research Data Repository Service.
categories: base-repo general
repository_url: https://github.com/kit-data-manager/base-repo
repository_name: kit-data-manager/base-repo
navigation_id: base_repo_index
---

# How to build

In order to build this microservice you'll need:

* Java SE Development Kit 8 or higher

After obtaining the sources change to the folder where the sources are located perform the following steps:

```
user@localhost:/home/user/base-repo$ ./gradlew -Pclean-release build
> Configure project :
Using release profile for building base-repo
<-------------> 0% EXECUTING [0s]
[...]
user@localhost:/home/user/base-repo$
```

The Gradle wrapper will now take care of downloading the configured version of Gradle, checking out all required libraries, build these
libraries and finally build the base-repo microservice itself. As a result, a fat jar containing the entire service is created at 'build/libs/base-repo.jar'.

# How to start

## Prerequisites

* PostgreSQL 9.1 or higher
* RabbitMQ 3.7.3 or higher (in case you want to use the messaging feature, which is recommended)

## Setup
Before you are able to start the repository microservice, you have to modify the file 'application.properties' according to your local setup.
Therefor, copy the file 'settings/application.properties' to your project folder and customize it. Special attentioned should be payed to the datasource url as well as
to the repository base path. Also, the property 'repo.messaging.enabled' should be changed to 'true' in case you want to use the messaging feature of the repository.

As soon as you finished modifying 'application.properties', you may start the repository microservice by executing the following command inside the project folder,
e.g. where the service has been built before:

```
user@localhost:/home/user/base-repo$ ./build/libs/base-repo.jar

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.0.5.RELEASE)
[...]
1970-01-01 00:00:00.000  INFO 56918 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''

```

If your 'application.properties' is not located inside the project folder you can provide it using 
the command line argument --spring.config.location=<PATH_TO_APPLICATION.PROPERTIES>

As soon as the microservice is started, you can browse to

http://localhost:8090/swagger-ui.html

in order to see available RESTful endpoints and their documentation. Furthermore, you can use this Web interface to test 
single API calls in order to get familiar with the service. A small documentation guiding you through the first steps 
of using the RESTful API you can find at

http://localhost:8090/static/docs/documentation.html

## Enhanced Startup

At certain points, base-repo offers and will offer extension points allowing to add custom features that are not part of 
the default distribution, e.g. custom message handlers. If you are familiar with software development, it might be no big 
deal to include an additional dependency to 'build.gradle' of base-repo. However, in some cases this might not be desirable 
or possible. Therefor, base-repo allows placing additional libraries required at runtime in a separate folder which is 
then loaded as soon as the microservice starts and made available using the dependency injection feature of Spring Boot.

In order to tell Spring Boot where to look for additional libraries, you have to define an environment variable JAVA_OPTS 
looking as follows:

```
export JAVA_OPTS="-cp .:./config:./base-repo.jar -Dloader.path=./base-repo.jar,./lib/,."
```

The first part '-cp' has to contain three elements divided by ':':

* The configuration folder where your application.properties is located (this element can be omitted, if application.properties is located in the current folder),
* the current folder,
* and the microservice jar file.

The second part '-Dloader.path' basically contains the same information as '-cp' but with the difference, that the 
config folder is not required, whereas the folder containing all additional libraries has to be provided, in our case 
it's './lib'.

Please keep in mind that all arguments shown in the example assume, that you are in the same folder where your microservice 
jar file is located and that you start the service by calling './base-repo.jar'. If your microservice jar is located 
elsewhere, you should consider providing absolute paths for all arguments above. In case you want to choose a different 
folder for placing your additional libraries, you have to rename it in JAVA_OPTS accordingly.

What you now have to do before you start the microservice is to place additional jar files (and required dependencies!) 
in the 'lib' folder. At the next startup, the new functionality should be available.
