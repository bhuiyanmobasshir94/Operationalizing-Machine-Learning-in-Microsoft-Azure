
# Operationalizing Machine Learning in Microsoft Azure

In this project,I will continue to work with the `Bank Marketing dataset`. I will use Azure to configure a cloud-based machine learning production model, deploy it, and consume it. I will also create, publish, and consume a pipeline.

## Project Main Steps

In this project, I will be following the below steps:
- Authentication
- Automated ML Experiment
- Deploy the best model
- Enable logging
- Swagger Documentation
- Consume model endpoints
- Create and publish a pipeline
- Documentation

## Architecture Design 
![Architecture Design](images/architecture.png)

## Future Improvements

Future Improvements can be done on data imbalance problem which was marked on the `Data Guardrails` of Runs. 

## Steps

### Authentication

As I am using the lab, Udacity provided to me, I am not authorized to create a security principal and so I skipped this step.

### Automated ML Experiment

In this step, I will create an experiment using Automated ML, configure a compute cluster, and use that cluster to run the experiment. 

What I am doing here is

- Creating an automl run with registered `Bank Marketing` dataset
- Creating a new compute cluster with VM STANDARD_DS12_V2 and minimum number of nodes 1
- Running the experiment with classification where Explain Best Model is enabled, Exit Criterion is default to 1 and Concurrency default to 5.

![Bank Marketing Dataset](images/bank-marketing-dataset.PNG)
![AutoML Dataset Steps](images/automl-dataset-step.PNG)
![Cluster](images/cluster.PNG)
![Exit Criterion](images/exit-criterion.PNG)
![Concurrency](images/concurrency.PNG)
![Classification](images/classification.PNG)
![Completed experiment](images/experiment-completed.PNG)
![Best Model List](images/best-model-list.PNG)
![Best Model](images/best-model.PNG)
![Metrics](images/metrics.PNG)

## Deploy the best model

After the experiment run completes, a summary of all the models and their metrics are shown, including explanations. The Best Model will be shown in the Details tab. In the Models tab, it will come up first (at the top). I am going to select the best model for deployment.

Deploying the Best Model will allow to interact with the HTTP API service and interact with the model by sending data over POST requests.

What I am doing here is

- Selecting the best model for deployment
- Deploying the model with authentication enabled and with Azure Container Instances (ACI)

![Deploy with ACI](images/deplyo-with-aci.PNG)
![Deployment Success](images/deploy-success.PNG)
![Endpoint URI](images/endpoint-uri.PNG)

## Enable logging and application insights

Now that the Best Model is deployed, enable Application Insights and retrieve logs. Although this is configurable at deploy time with a check-box, it is useful to be able to run code that will enable it for you.

What I am doing here is

- Executing `logs.py` file to enable logging and application insights

![Azure Login](images/azure-login.PNG)
![Logging](images/logging.PNG)
![Application Insights](images/application-insigths.PNG)

## Swagger Documentation

In this step, I will consume the deployed model using Swagger to view and understand request and response payload

What I am doing here is

- Executing `swagger.sh` to run swagger server
- Serving deployed model's `swagger.json` via `serve.py` to demonstrate HTTP API endpoints and payloads

![Swagger Running](images/swagger-running.PNG)
![Swagger Serve](images/swagger-serve.PNG)
![Swagger Model](images/swagger-model.PNG)
![Swagger Display](images/swagger-display.PNG)
![Swagger Response](images/swagger-response.PNG)
![Swagger Response](images/swagger-response_2.PNG)


## Consume model endpoints

Once the model is deployed, using the `endpoint.py` script provided to interact with the trained model. In this step, I will run the script, modifying both the `scoring_uri` and the `key` to match the key for my service and the URI that was generated after deployment.

What I am doing here is

- Modifying the script and executing it

![Endpoint Success](images/endpoint-success.PNG)

It is an optional step. I want to load-test my model

What I am doing here is

- using `data.json` generated by `endpoint.py` file and apache load balancer tool `ab` to load test my model and check the performance measure, this is basically the benchmarking process

![Benchmarking](images/benchmark-1.PNG)
![Benchmarking](images/benchmark-2.PNG)

## Create and publish a pipeline

Here I am  using the Jupyter Notebook provided in the starter files. I am updating the notebook to have the same keys, URI, dataset, cluster, and model names already created. 

What I am doing here is

- Creating pipelines through azure ml python sdk
- Showing pipeline and published pipeline runs, best models and its performances etc

![Creating pipeline](images/pipeline-created.PNG)
![Pipeline show widget](images/pipeline-run-show-widget.PNG)
![Dataset](images/dataset-with-automl-module.PNG)
![Pipelines](images/pipelines.PNG)
![Pipeline Completed](images/pipeline-completed.PNG)
![Pipeline Rest Endpoint](images/pipeline-rest-endpoint.PNG)
![Pipeline Endpoint](images/pipeline-endpoint.PNG)
![Published Pipeline](images/published-pipeline.PNG)

## Core Services

Here are the core services used in this project

![Experiments](images/experiments.PNG)
![AutoMLs](images/automls.PNG)
![Datasets](images/datasets.PNG)
![Scheduled Run](images/scheduled-run.PNG)

## Screencast

Here is my screen cast video uploaded on Youtube - [link](https://youtu.be/385CrB2Di5Y)



