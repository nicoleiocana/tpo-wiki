Projects in the WEB group use a loose git workflow. 

Staging, Develop and Master Branches

Instead of a single *master* branch, this workflow uses **two** branches to record the history of the project and one extra branch to test out features and changes on our staging environment. The *master* branch stores the official release history, the *develop* branch serves as an integration branch for features, finally the *staging* branch has to be considered a dirty branch that can be overwritten and used for testing new features. 

## How to send a merge request or propose a change

1.  Make a clone of the tor git repository. All the repositories in the WEB group have a single source of truth: [https://gitweb.torproject.org/project/web/](https://gitweb.torproject.org/project/web/)

It is recommended that you clone from tor git even if you want to create a repository under your user space in dip.

2.  Create a new branch for the changes you want to make and start editing the files you want. Gitlab will suggest to create a merge request. You can share the merge request link with the others developers to have the change merged.

If you are not used to work with git, you can edit our websites content via dip (gitlab) directly. Here is a doc on how to use dip without getting involved with git: [https://dip.torproject.org/web/tpo/wikis/Use-dip-to-edit-websites](https://dip.torproject.org/web/tpo/wikis/Use-dip-to-edit-websites)

## How to merge from a branch or third party repository.

When you are merging from a branch or third party repository make sure to edit the commit message in a way that other contributors now what you are doing.

If you wanted to be nicer you could also simply merge commits from the branch so that you keep the commit messages of the initial contributor.

