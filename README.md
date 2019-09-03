# Maven-repo-test

This is a sample repository to test whether subtree and maven-build works for these modules: kie-soup, droolsjbpm-knowledge and drools. In order to run this repository, ensure that you have subtrees configured, please refer to [references](#References) section below to configure it.

## Build 

In order to build this, run this command.

`mvn clean install -DskipTests -P nestrepos`

A `nestrepos` profile has been created inside `pom.xml` including the above modules.

## Steps to reproduce
(you needn’t follow these instructions, this has already been done for you) Add the subtree remote using: `git remote add -f kogito-wiki https://github.com/kiegroup/kogito-runtimes.wiki.git`

Add the subtree using(creates a commit automatically): `git subtree add --prefix=kogito-wiki https://github.com/kiegroup/kogito-runtimes.wiki.git master`

Pull the latest updates from subtree: `git subtree pull-all`

References:

[Git subtree module, with .gittrees config file](https://ruleant.blogspot.com/2013/06/git-subtree-module-with-gittrees-config.html)


