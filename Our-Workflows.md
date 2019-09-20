## Our Workflows

### Internal Workflow

This is the workflow that Tor Internal people should use when making changes on the Community Portal:

1. When starting work on an issue or content, please assign the issue to yourself and move into the `Doing` column on the [Community Portal Project Board](https://dip.torproject.org/web/community/-/boards). You can follow the process outlined in ["How to send a merge request or propose a change"](https://dip.torproject.org/web/tpo/wikis/Git-flow-and-merge-requests#how-to-send-a-merge-request-or-propose-a-change) to work on your changes. e.g
```
# Start a new feature
git checkout -b new-feature master
# Edit some files
git add <file>
git commit -m "Start a feature"
# Edit some files
git add <file>
git commit -m "Finish a feature"
```
2. To view your changes on the website, you can [run lektor locally](https://dip.torproject.org/web/tpo/wikis/Compiling-a-local-version-of-the-website)
3. Once you are happy with your work, push your changes to `develop` branch and move to `needs-review` column on the [Community Portal Project Board](https://dip.torproject.org/web/community/-/boards)
4. Add a comment to the issue, tagging the reviewer, e.g `@steph`, with:
    - Location of page on lektor-staging `develop` branch, e.g https://lektor-staging.torproject.org/community/develop/
    - Contents file, containing your changes where it would be located on the **reviewer's repo** e.g `https://dip.torproject.org/steph/community/blob/develop/content/onion-services/contents.lr` 
    - For the review workflow, please see [Review Workflow]()
5. Once the work has been reviewed and any necessary changes have been made, reviewer will move the issue to the `reviewed` column and add a comment with the link to the merge request on **their repo** e.g https://dip.torproject.org/steph/community/merge_requests/1
6. Team members with write access to gitweb master will then merge or cherry-pick these changes to master, following the workflow outlined in [How to use our git flow](https://dip.torproject.org/web/tpo/wikis/Git-flow-and-merge-requests#how-to-use-our-git-flow)
7. Merger should then move the the ticket to the `Closed` column

### Volunteer Workflow

This is the workflow that external volunteers should use when making changes on the Community Portal:

We recommend that you use our [github mirror](https://github.com/torproject/community) to submit PRs and contributions to our Community repo. Once you have a PR ready you should:

0. Ideally try to run it locally and check that nothing breaks and everything still behaves as before
1. Make a PR and ping the team on #tor-www IRC channel to let us know there's a PR waiting for reviewx

At this point, one of us on the website team will aim to review your PR within 24h during the week (this may take longer on the weekends). Review will involve:

  - Reading the text to make sure it's accurate and there are no spelling errors or grammar mistakes
  - If there are any front end and/or template changes involved, the changes will be pushed to our development branch for functionality review
  - If there are any fixes necessary, we will ask for changes to be made.

Once it all looks good and behaves correctly, we will merge your request to the master branch of the community portal [canonical repo](https://gitweb.torproject.org/project/web/community.git/) on [gitweb](https://gitweb.torproject.org/) master. 

### Review Workflow

1. 

