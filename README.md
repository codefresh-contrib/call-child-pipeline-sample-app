# Example for using the codefresh-run plugin to call other pipelines

This is an example application for the Codefresh CI/CD platform that contains a parent pipeline that call two other pipelines (QA or production deployment) according to the branch name.

To call another pipeline the [codefresh-run plugin](https://codefresh.io/steps/step/codefresh-run) is used.


## The sample application

There is a dummy NodeJs application in the same repository that is used for the creation of a Docker image.
The first step of the pipeline read the `package.json` file to extract the version of the application.

The application version is then used as the tag of the Docker image as well as a parameter to the downstream
pipelines.


## To use this project in Codefresh

1. Create a QA child pipeline using the contents of [codefresh-qa.yml](codefresh-qa.yml)
1. Create a Prod child pipeline using the contents of [codefresh-prod.yml](codefresh-prod.yml)
1. Create a parent pipeline using the contents of [codefresh.yml](codefresh.yml) and attach a Git trigger to it.

More details can be found in [Codefresh documentation](https://codefresh.io/docs/docs/yaml-examples/examples/call-child-pipelines/)

