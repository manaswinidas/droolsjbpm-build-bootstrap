# Maven-repo-test

This is a sample repository to test whether subtree and maven-build works for these modules: kie-soup, droolsjbpm-knowledge and drools.

## Build 

In order to build this, run this command.

`mvn clean install -DskipTests -P nestrepos`

A `nestrepos` profile has been created inside `pom.xml` including the above modules.

## Steps to reproduce

### Adding a new repository as a subtree

1. Add a new remote URL pointing to the separate project that we're interested in.

For example, for adding drools, we can execute the following command:

`git remote add -f drools git@github.com:kiegroup/drools.git`

2. Merge the Spoon-Knife project into the local Git project. This doesn't change any of your files locally, but it does prepare Git for the next step.

If you're using Git 2.9 or above:

`git merge -s ours --no-commit --allow-unrelated-histories drools/master`

If you're using Git 2.8 or below:

`git merge -s ours --no-commit drools/master`

3. Create a new directory called spoon-knife, and copy the Git history of the Spoon-Knife project into it.

`git read-tree --prefix=drools/ -u drools/master`

You can commit to save your work. 

### Synchronizing with updates and changes

When a subproject is added, it is not automatically kept in sync with the upstream changes. You will need to update the subproject with the following command:

`git pull -s subtree remotename branchname`

For the example above, this would be:

$ git pull -s subtree drools master

References:
[Git subtree: the alternative to Git submodule-Atlassian](https://www.atlassian.com/blog/git/alternatives-to-git-submodule-git-subtree#How)

[About Git subtree merges-GitHub](https://help.github.com/en/articles/about-git-subtree-merges)



