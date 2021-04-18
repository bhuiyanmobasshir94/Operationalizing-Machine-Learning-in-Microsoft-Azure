Does this setup need to be done to prevent these errors:
You will need to do the following to be successful with the rest of the notebook:

Have an existing Azure subscription. You can get started for free here

Understand the architecture and terms introduced by Azure Machine Learning service (AzureML)

Make sure the AzureML Python SDK is installed with notebooks and contrib add ons.

    conda create -n azureml -y Python=3.6
    source activate azureml
    pip install --upgrade azureml-sdk[notebooks,contrib] 
    conda install ipywidgets
    jupyter nbextension install --py --user azureml.widgets
    jupyter nbextension enable azureml.widgets --user --py

    Import the required packages

    Set Environment Variables

    Connect to an Azure Machine Learning service workspace
 
Ref: [.](https://github.com/microsoft/nlp-recipes/issues/379#issuecomment-525537434)
