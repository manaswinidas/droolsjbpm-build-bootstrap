# Maven-repo-test

This is a sample repository to test whether subtree and maven-build works for these modules: kie-soup, droolsjbpm-knowledge and drools.

## Build 

In order to build this, a `nestrepos` profile has been created inside `pom.xml` in `mvn-repo-test`.

`cd mvn-repo-test`

`mvn clean install -DskipTests -P nestrepos`