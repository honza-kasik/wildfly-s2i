# EJB, JSF and JPA example.

In this example we are provisioning a WildFly server and deploying a JSF application.

# WildFly Maven plugin configuration
High level view of the WildFly Maven plugin configuration

## Galleon feature-packs

* `org.wildfly:wildfly-galleon-pack`

## Galleon layers

* `cloud-server`
* `ejb-lite`
* `jsf`
* `jpa`
* `h2-driver`

## CLI scripts
WildFly CLI scripts executed at packaging time

* None

## Extra content
Extra content packaged inside the provisioned server

* None

# Openshift build and deployment
Technologies required to build and deploy this example

* WildFly Helm charts `wildfly_v2/wildfly`

# WildFly image API
Environment variables from the [WildFly image API](https://github.com/wildfly/wildfly-cekit-modules/blob/v2/jboss/container/wildfly/run/api/module.yaml) that must be set in the OpenShift deployment environment

* None

# Pre-requisites

* You are logged into an OpenShift cluster and have `oc` command in your path

* You have installed Helm. Please refer to [Installing Helm page](https://helm.sh/docs/intro/install/) to install Helm in your environment

* You have installed WildFly Helm charts for WildFly s2i V2

 ```
helm repo add wildfly_v2 https://jmesnil.github.io/wildfly-charts/
```

# Example steps

1. Deploy the example application using WildFly Helm charts

```
helm install jsf-ejb-jpa-app -f helm.yaml wildfly_v2/wildfly
```

2. You can then access the application: `https://<jsf-ejb-jpa-app host>/`. You will see pre-populated tasks. You can add / delete tasks. 

