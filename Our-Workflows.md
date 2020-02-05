This is a tentative workflow that people should use when contributing to www sites.
Some specific websites might have specific rules, but all follow these general guidelines.

If you are a recurring contributor, you should follow the [Gitlab workflow](#gitlab-workflow).
If you are just starting to contribute, you should follow the [Github workflow](#github-workflow). If you have been a contributor for a while, we should make you a gitlab account. So please reach out and we can help you with that.


## Gitlab Workflow

This is the workflow that recurring contributors to the websites with a dip.torproject.org account should use when making changes to the Websites:

1. When starting work on an issue or content, please assign the issue to yourself and move into the `Doing` column on the relevant Project Board.
You can follow the process outlined in [Git flow and merge requests](Git-flow-and-merge-requests#how-to-send-a-merge-request-or-propose-a-change) to work on your changes.
2. To view your changes on the website, you can follow the instructions for [Compiling a local version of the website](Compiling-a-local-version-of-the-website).
3. Once you are happy with your work, push your changes to `develop` branch and move to `needs-review` column on the project board.
4. Add a comment to the issue, tagging the reviewer, e.g `@steph`, with:
    - Location of page on lektor-staging `develop` branch, e.g https://lektor-staging.torproject.org/community/develop/
    - Contents file, containing your changes where it would be located on the **reviewer's repo** e.g `https://dip.torproject.org/steph/community/blob/develop/content/onion-services/contents.lr` 
    - For the review workflow, please see the [Reviewer Workflow](Our-Workflows#reviewer-workflow) below.
5. Once the work has been reviewed and any necessary changes and merge request has been made, a repo maintainer or team members with write access to gitweb master will then merge or cherry-pick these changes to master, following the workflow outlined in [Git flow and merge requests](Git-flow-and-merge-requests#how-to-use-our-git-flow)
6. Merger should then move the the ticket to the `Closed` column.


## Github Workflow

This is the workflow that people without a dip account should use when making changes on the various torproject.org websites.

If you are comfortable using gitlab we have setup [github mirrors](https://github.com/orgs/torproject/teams/web/repositories) for all our websites.

If you want to contribute to a specific issue, you can comment on the issue itself or contact one of the WWW contributors. Once you have a Pull Request ready to merge you should:

0. Ideally try to run it locally and check that nothing breaks and everything still behaves as before. If you need help with running Lektor or building the website locally please reach out.
1. Make a PR via github or any other git service and comment on the issue mentioning the PR link. If you want you can also reach out to the team on #tor-www IRC channel to let us know.

At this point, one of us on the website team will aim to review your PR.
When we review a PR we make sure that the text it's accurate and there are no spelling errors or grammar mistakes. Then if:

  - There are any front end and/or template changes involved, the changes will be pushed to our `develop` branch for functionality review
  - There are any fixes necessary, we will ask for changes to be made.

Once it all looks good and behaves correctly, we will merge your request to the master branch of the community portal [canonical repo](https://gitweb.torproject.org/project/web/community.git/) on [gitweb](https://gitweb.torproject.org/) master. 


## Reviewer Workflow

1. Review the page on lektor-staging, e.g https://lektor-staging.torproject.org/community/staging/
2. Review the content on **your repo's** develop branch and use the gitlab edit button to make any changes, e.g `https://dip.torproject.org/<your-gitlab-user>/community/blob/develop/content/onion-services/contents.lr` 
3. When you are happy with your changes:
    - Update the "Commit message" to explain why you have made your changes
    - Update the "Target Branch"
    - Make sure that the "Start a new merge request with these changes" checkbox is checked.
    - Click on "Commit changes"
4. You will be sent to a new page to create your merge request:
    - Update "Title" with a short title to explain your changes
    - Update "Description", you can use the commit message you entered before additionally referencing the original issue you have reviewed, e.g `https://dip.torproject.org/web/community/issues/3` and tagging one of the repo maintainers e.g `@pili` so they know the change can be merged
    - Make sure that both "Delete source branch when merge request is accepted" and "Squash commits when merge request is accepted" are checked.
    - Click "Submit merge request"
5. Reviewer should comment on the original issue with a link to the merge request created, e.g `https://dip.torproject.org/steph/community/merge_requests/2`

