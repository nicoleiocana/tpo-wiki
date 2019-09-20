## Tor Internal Workflow

This is the workflow that Tor Internal people should use when making changes to the Websites:

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

## Reviewer Workflow

1. Review the page on lektor-staging, e.g https://lektor-staging.torproject.org/community/develop/
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

## Volunteer Workflow

This is the workflow that external volunteers should use when making changes on the Community Portal:

We recommend that you use our [github mirror](https://github.com/torproject/community) to submit PRs and contributions to our Community repo. Once you have a PR ready you should:

0. Ideally try to run it locally and check that nothing breaks and everything still behaves as before
1. Make a PR and ping the team on #tor-www IRC channel to let us know there's a PR waiting for review

At this point, one of us on the website team will aim to review your PR within 24h during the week (this may take longer on the weekends). Review will involve:

  - Reading the text to make sure it's accurate and there are no spelling errors or grammar mistakes
  - If there are any front end and/or template changes involved, the changes will be pushed to our `develop` branch for functionality review
  - If there are any fixes necessary, we will ask for changes to be made.

Once it all looks good and behaves correctly, we will merge your request to the master branch of the community portal [canonical repo](https://gitweb.torproject.org/project/web/community.git/) on [gitweb](https://gitweb.torproject.org/) master. 