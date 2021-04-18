
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

## Steps

### Authentication

As I am using the lab, Udacity provided to me, I am not authorized to create a security principal and so I skipped this step.

### Automated ML Experiment

In this step, I will create an experiment using Automated ML, configure a compute cluster, and use that cluster to run the experiment. 

What I am doing here is

- Creating an automl run with registered `Bank Marketing` dataset
- Creating a new compute cluster with VM STANDARD_DS12_V2 and minimum number of nodes 1
- Running the experiment with classification where Explain Best Model is enabled, Exit Criterion is default to 1 and Concurrency default to 5.



