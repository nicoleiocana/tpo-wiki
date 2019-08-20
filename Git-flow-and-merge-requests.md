Projects in the WEB group use a loose git workflow. 

Staging, Develop and Master Branches

Instead of a single *master* branch, this workflow uses **two** branches to record the history of the project and one extra branch to test out features and changes on our staging environment. The *master* branch stores the official release history, the *develop* branch serves as an integration branch for features, finally the *staging* branch has to be considered a dirty branch that can be overwritten and used for testing new features. 

## How to send a merge request or propose a change

1.  Make a clone of the tor git repository. All the repositories in the WEB group have a single source of truth: [https://gitweb.torproject.org/project/web/](https://gitweb.torproject.org/project/web/)

It is recommended that you clone from tor git even if you want to create a repository under your user space in dip.

To clone a tor git repository in dip:

1.  Go to your projects dashboard: [https://dip.torproject.org/dashboard/projects](https://dip.torproject.org/dashboard/projects) 

2.  Click on the + icon next to the search box. And on "New Project"

![newproject](uploads/d0bda1942a3879283d0eceaf921dd19e/newproject.png)

3.  Got to the project you want to clone on tor git and select the clone link

![tor-git](uploads/e148061d70aa8c8d98ab0674d9442c0d/tor-git.png)

4. Use the link to clone the repository in dip by clicking on "Import Project" in the new project page

![import-project](uploads/36cef13e2cd46de3020165892d370863/import-project.png)

## How to merge from a third party branch/repository.

