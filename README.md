# trigger-pipeline-demo
Demo of manually triggering a CircleCI pipeline

This demo showcases how we can set up a workflow to be triggered manually / on-demand via the [TriggerPipeline API](https://circleci.com/docs/api/v2/#operation/triggerPipeline).

The added benefit is that, we can also trigger the pipeline via the CircleCI build UI itself (see below screenshots).

For this example, we want to trigger the workflow in our pipeline on the `release` branch only.
