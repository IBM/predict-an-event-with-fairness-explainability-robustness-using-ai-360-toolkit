# Predict an event with fairness, explainability & robustness using AI fairness 360 toolkit.
`In this Code Pattern, we will use diabetes data to predict whether a person is prone to have diabetes or not. We will explore Fairness, explainability & robustness of the predictive models and enhance the effectiveness of the AI predictive system.`  

The Code Pattern demonstrates the end-to-end solution : 
- Check the Fairness of the Diabetes Dataset using the Fairness Tool kit.
- Develop the Model.
- Explain the Model using the Explainability toolkit.

The Code Pattern shares the generic code template for the entire end-to-end process of the above three steps. Therefore, it can used to plugin any Dataset that a developer wants to explore the fairness and explainability for.

## What is Fairness?
Fairness is the process of understanding bias introduced by your data, and ensuring your model provides equitable predictions across all demographic groups. Rather than thinking of fairness as a separate initiative, it’s important to apply fairness analysis throughout your entire ML process, making sure to continuously reevaluate your models from the perspective of fairness and inclusion. This is especially important when AI is deployed in critical business processes, like credit application reviews and fraud detection, that affect a wide range of end users. 

## How does the fairness algorithm work?

The bias mitigation algorithm can be applied in three different stages of model building. These stages are `pre-processing, in-processing & post-processing.` The below diagram demonstrates how it works. 

![](https://github.com/IBM/predict-an-event-with-fairness-explainability-robustness-using-ai-360-toolkit/blob/main/doc/source/images/aif-360-flow.png)

The AIF360 Python package contains nine different algorithms, developed by the broader algorithmic fairness research community, to mitigate that unwanted bias. They can all be called in a standard way, very similar to scikit-learn’s fit/predict paradigm. 

For specific details refer to the Code Pattern: 

## What is Explainability? 
Explainability of a Machine Learning Model refers to unveiling of the black box model which just makes the prediction or give the recommendation to the White box which actually gives the details of the underlying mechanism and pattern identified by the model for a particular Dataset. There are multiple reasons why we need to understand the underlying mechanism of the Machine learning Models
- Human Readability.
- Bias Mitigation.
- Justifiability.
- Interpretability.

<img src="https://github.com/IBM/unveiling-machine-fraud-prediction-decision-with-ai-explainability-360/blob/main/doc/source/images/AIX360_1.png" width="1000" height="500" />

## How does Explainability work? 
[AI Explainability 360](http://aix360.mybluemix.net/), a comprehensive open source toolkit of state-of-the-art algorithms that support the interpretability and explainability of machine learning models. Currently, AI explainability 360 toolkit provides eight state-of-the-art explainability algorithms that can add transparency throughout AI systems. Depending on the requirement and subjected to the problem statement you can choose them appropriately. The algorithms are explained in detail on this [link.](https://aix360.mybluemix.net/))

For specific details refer to this [Code Pattern](https://github.com/IBM/unveiling-machine-fraud-prediction-decision-with-ai-explainability-360)


## Architecture diagram

![](https://github.com/IBM/predict-an-event-with-fairness-explainability-robustness-using-ai-360-toolkit/blob/main/doc/source/images/architecture.png)

### Flow

1. Log in to Watson Studio powered by spark, initiate Cloud Object Storage, and  create a project.
2. Upload the .csv data file to Object Storage.
3. Load the Data File in Watson Studio Notebook.
4. Install `aif 360` and `aix 360` Toolkit in the Watson Studio Notebook. 
run :
```
!pip install aix360 

!pip install aif360
```
5. Analyze the results after applying the bias mitigation algorithm during pre-processing, in-processing & post-processing stages.

## Included components

* [IBM Watson Studio](https://www.ibm.com/cloud/watson-studio): Analyze data using RStudio, Jupyter, and Python in a configured, collaborative environment that includes IBM value-adds, such as managed Spark.

* [IBM AI Fairness 360 toolkit](https://www.ibm.com/blogs/research/2018/09/ai-fairness-360/): AI Fairness 360 (AIF360), a comprehensive open-source toolkit of metrics to check for unwanted bias in datasets and machine learning models, and state-of-the-art algorithms to mitigate such bias. 

* [IBM AI Explainability 360 ](https://www.ibm.com/blogs/research/2019/08/ai-explainability-360/): The AI Explainability 360 toolkit is an open-source library that supports interpretability and explainability of datasets and machine learning models. The AI Explainability 360 Python package includes a comprehensive set of algorithms that cover different dimensions of explanations along with proxy explainability metrics.

* [IBM Adverserial Robustness ](https://github.com/Trusted-AI/adversarial-robustness-toolbox): Adversarial Robustness Toolbox (ART) is a Python library for Machine Learning Security. ART provides tools that enable developers and researchers to defend and evaluate Machine Learning models and applications against the adversarial threats of Evasion, Poisoning, Extraction, and Inference.

* [IBM Cloud Object Storage](https://console.bluemix.net/catalog/services/cloud-object-storage): An IBM Cloud service that provides an unstructured cloud data store to build and deliver cost effective apps and services with high reliability and fast speed to market. This code pattern uses Cloud Object Storage.


## Featured technologies

* [Artificial Intelligence](https://developer.ibm.com/technologies/artificial-intelligence/): Any system which can mimic cognitive functions that humans associate with the human mind, such as learning and problem solving.
* [Data Science](https://developer.ibm.com/code/technologies/data-science/): Systems and scientific methods to analyze structured and unstructured data in order to extract knowledge and insights.
* [Analytics](https://developer.ibm.com/code/technologies/analytics/): Analytics delivers the value of data for the enterprise.
* [Python](https://www.python.org/): Python is a programming language that lets you work more quickly and integrate your systems more effectively.

## Steps using AIF 360 on Watson Studio


1. [Create an account with IBM Cloud](#1-create-an-account-with-ibm-cloud)
1. [Create a new Watson Studio project](#2-create-a-new-watson-studio-project)
1. [Add Data](#3-add-data)
1. [Create the notebook](#4-create-the-notebook)
1. [Insert the data as dataframe](#5-insert-the-data-as-dataframe)
1. [Run the notebook](#6-run-the-notebook)
1. [Analyze the results](#7-analyze-the-results)

## 1. Create an account with IBM Cloud

Sign up for IBM [**Cloud**](https://console.bluemix.net/). By clicking on create a free account you will get 30 days trial account.

## 2. Create a new Watson Studio project

Sign up for IBM's [Watson Studio](http://dataplatform.cloud.ibm.com/). 

Click on New Project and select per below.

![](https://github.com/IBM/predict-an-event-with-fairness-explainability-robustness-using-ai-360-toolkit/blob/main/doc/source/images/create_prj.png)

Define the project by giving a Name and hit 'Create'.

![](https://github.com/IBM/predict-an-event-with-fairness-explainability-robustness-using-ai-360-toolkit/blob/main/doc/source/images/def-prj.png)

## 3. Add Data

[Clone this repo](https://github.com/IBM/predict-an-event-with-fairness-explainability-robustness-using-ai-360-toolkit)
Navigate to [data/assets](https://github.com/IBM/bias-mitigation-of-machine-learning-models-using-aif360/tree/main/data/assets) and save the file by name `diabetes_data.csv` on the disk. The zip file `Pipeline_LabelEncoder-0.1.zip` also needs to be saved onto the disk. 

Click on Assets and select Browse and add the csv file from your file system. Repeat the step and add the zip file as an asset. 

![](https://github.com/IBM/predict-an-event-with-fairness-explainability-robustness-using-ai-360-toolkit/blob/main/doc/source/images/add_asset.png)

## 4. Create the notebook

* Open [IBM Watson Studio](https://dataplatform.ibm.com).
* Go to the project and click on Add 
* Click on `Create notebook` to create a notebook.
* Select the `From URL` tab.
* Enter a name for the notebook.
* Optionally, enter a description for the notebook.
* Enter this Notebook URL for Fairness : https://github.com/IBM/predict-an-event-with-fairness-explainability-robustness-using-ai-360-toolkit/blob/main/notebooks/Fairness.ipynb
* Enter this Notebook URL for Explainability & Robustness : https://github.com/IBM/predict-an-event-with-fairness-explainability-robustness-using-ai-360-toolkit/blob/main/notebooks/Explainability.ipynb
* Select the runtime (2 vCPU and 8 GB RAM.)
* Click the `Create` button.

After the notebooks are imported, click on `Not Trusted` and select the option as Yes to trust the source of the notebooks.

![](https://github.com/IBM/bias-mitigation-of-machine-learning-models-using-aif360/blob/main/images/not_trusted.png)

`This notebook has been created to demonstrate the steps for building the model using Watson Studio platform for fraud prediction usecase. For other usecases, the notebook has to be modified to read the new dataset and the same steps can be executed.`

## 5. Insert the data as dataframe

Click on 0010 icon at the top right side which will bring up the data assets tab.

![](https://github.com/IBM/bias-mitigation-of-machine-learning-models-using-aif360/blob/main/images/add.png)

Click on Insert to code dropdown and select the option Insert Pandas Dataframe.

![](https://github.com/IBM/bias-mitigation-of-machine-learning-models-using-aif360/blob/main/images/insert_dataframe.png)

## 6. Run the notebook

When a notebook is executed, what is actually happening is that each code cell in
the notebook is executed, in order, from top to bottom.

Each code cell is selectable and is preceded by a tag in the left margin. The tag
format is `In [x]:`. Depending on the state of the notebook, the `x` can be:

* A blank, this indicates that the cell has never been executed.
* A number, this number represents the relative order this code step was executed.
* A `*`, this indicates that the cell is currently executing.

There are several ways to execute the code cells in your notebook:

* One cell at a time.
  * Select the cell, and then press the `Play` button in the toolbar.
* Batch mode, in sequential order.
  * From the `Cell` menu bar, there are several options available. For example, you
    can `Run All` cells in your notebook, or you can `Run All Below`, that will
    start executing from the first cell under the currently selected cell, and then
    continue executing all cells that follow.

## 7. Analyze the results

After we run all cells in the notebook, the results are displayed at the end of each notebook per below.
