# Maven-repo-test

This is a sample repository to test whether subtree and maven-build works for these modules: kie-soup, droolsjbpm-knowledge and drools.

## Build 

In order to build this, run this command.

`mvn clean install -DskipTests -P nestrepos`

A `nestrepos` profile has been created inside `pom.xml` including the above modules.