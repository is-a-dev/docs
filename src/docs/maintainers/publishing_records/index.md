# Publishing records
> NOTE: This is only for maintainers with publishing access.

Currently, the records are published using a manual GitHub actions workflow.
When all the PR's are merged and ready:

1. Go to `Actions > Publish records`.
1. Click `Run workflow` button to publish merged records.

## Error
Sometimes it may log an error message while publishing saying some record(s) couldn't be published.
Usually, the cause is related to some conflict while deleting and re-publishing.
In those situations, running the workflow again will fix the issues.
