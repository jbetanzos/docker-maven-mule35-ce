# Dockerfile for Mule Server 3.5 with Maven

This *Automated Builds* uses a Maven 3.3 with JDK 8. Mule 3.5 runtime.

In order to create the docker container you can follow the next command.
```
$ docker run -d ——name <container_name> -p 8083:8083 -P -v <local_directory>:/opt/mule/apps jbetanzos/maven-mule-35
```
By default the Mule Server is expose to 8083. You can link the Mule application container to a local directory, change the tag <local_directory> to your own configuration. You can also change the <container_name> for a custom name.

You can run `$ docker logs <container_name>` in order to check the mule logs and verify that everything is running. 
```
docker logs mule_ce_35
INFO  2015-08-13 16:02:57,701 [WrapperListener_start_runner] org.mule.module.launcher.DeploymentDirectoryWatcher: 
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+ Mule is up and kicking (every 5000ms)                    +
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
INFO  2015-08-13 16:02:57,785 [WrapperListener_start_runner] org.mule.module.launcher.StartupSummaryDeploymentListener: 
**********************************************************************
*              - - + DOMAIN + - -               * - - + STATUS + - - *
**********************************************************************
* default                                       * DEPLOYED           *
**********************************************************************
```
You can also check if the container is running correctly with `$ docker ps`. Output example:
```
$ docker ps
CONTAINER ID        IMAGE                       COMMAND                CREATED             STATUS                      PORTS                    NAMES
1fbfc5275e4e        jbetanzos/maven-mule-35     “/opt/mule/bin/mule”   19 hours ago        Up 9 seconds                0.0.0.0:8083->8083/tcp   mule_ce_35
```
