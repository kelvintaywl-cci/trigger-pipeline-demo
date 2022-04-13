# trigger-pipeline-demo
Demo of manually triggering a CircleCI pipeline

This demo showcases how we can set up a workflow to be triggered manually / on-demand via the [TriggerPipeline API](https://circleci.com/docs/api/v2/#operation/triggerPipeline).

The added benefit is that, we can also trigger the pipeline via the CircleCI UI itself (see below screenshots).

For this example, we want to trigger the `manually-triggered` workflow in our pipeline, on the `release` branch only.
Please see [the _.circleci/config.yml_ file](.circleci/config.yml) for the defintions.


## How to trigger the workflow via TriggerPipeline API?

You can do so in 2 ways, (1) directly invoking via HTTP API, or (2) via the CircleCI UI.

Option 1: via API

```console
# please include your CircleCI personal access token, and replace the project slug.

$ curl --request POST \
  --url https://circleci.com/api/v2/project/gh/kelvintaywl-cci/trigger-pipeline-demo/pipeline \
  --header "Circle-Token: $CIRCLE_TOKEN" \
  --header 'content-type: application/json' \
  --data '{"branch":"release","parameters":{}}'
```


Option 2: via UI

1. Go to the project dashboard itself, e.g.
2. Click on `Trigger Pipeline` button, and fill in pipeline parameters as required.
3. Trigger the pipeline, and verify the workflow and jobs have started.

<img width="1257" alt="01_filter_branch" src="https://user-images.githubusercontent.com/2164346/163089075-7782e380-3609-4b21-abdb-18b510c29033.png">
<img width="489" alt="02_trigger_pipeline" src="https://user-images.githubusercontent.com/2164346/163089100-16e6a527-e3d2-482a-ab58-7a92dd395784.png">
<img width="646" alt="03_job_has_ran" src="https://user-images.githubusercontent.com/2164346/163089134-47bbca33-fc19-450e-9860-49a04291227c.png">


