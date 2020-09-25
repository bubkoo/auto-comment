> Github action to comment issues or PRs on events triggered.

## Usage

Create a `.github/workflows/auto-comment.yml` file in the repository you want to install this action, then add the following to it:

```yml
name: Auto Comment
on: [issues, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: bubkoo/auto-comment@v1
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          issuesOpened: >
            👋 @${author}
            
            Thank your for raising a issue. We will try and get back to you as soon as possible.
            
            Please make sure you have given us as much context as possible.


          pullRequestOpened: >
            👋 @${author}
            
            Thank your for raising your pull request.
            
            Please make sure you have followed our contributing guidelines. We will review it as soon as possible
```

There are a couple of events that you will need to setup depending on what you want.

### Available Events

- issuesOpened
- issuesEdited
- issuesDeleted
- issuesTransferred
- issuesPinned
- issuesUnpinned
- issuesClosed
- issuesReopened
- issuesAssigned
- issuesUnassigned
- issuesLabeled
- issuesUnlabeled
- issuesLocked
- issuesUnlocked
- issuesMilestoned
- issuesDemilestoned

- pullRequestAssigned
- pullRequestUnassigned
- pullRequestLabeled
- pullRequestUnlabeled
- pullRequestEdited
- pullRequestOpened
- pullRequestClosed
- pullRequestReopened
- pullRequestSynchronize
- pullRequestReadyForReview
- pullRequestLocked
- pullRequestUnlocked
- pullRequestReviewRequested
- pullRequestReviewRequestRemoved
