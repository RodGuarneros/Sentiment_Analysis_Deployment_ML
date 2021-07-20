# Sentiment Analysis Deployment Model
### By Rodrigo Guarneros

## Objective

<b>Here you can find a web application aimed to forecast if a movie review previously written is positive or negative</b>. This model was built with a particular module in Amazon Web Services: SageMaker using [XGBoost](https://xgboost.readthedocs.io/en/latest/) (A optimized distributed gradient boosting library designed to be highly efficient, flexible and portable) as well as [PyTorch for a Artifical Neural Network](https://pytorch.org/tutorials/beginner/blitz/neural_networks_tutorial.html), based on Python language.

## Results example

The web app is available at: https://rodguarneros.github.io/Sentiment_Analysis_Deployment_ML/ 

### The Web App looks like this:
![Result1.jpg](https://github.com/RodGuarneros/Sentiment_Analysis_Deployment_ML/blob/main/images/Result1.jpg)

### If you write a positive movie review up, the result is:
![Result2.jpg](https://github.com/RodGuarneros/Sentiment_Analysis_Deployment_ML/blob/main/images/Result2.jpg)

### If you write a negative movie review up, the result is:
![Result3.jpg](https://github.com/RodGuarneros/Sentiment_Analysis_Deployment_ML/blob/main/images/Result3.jpg)


## General Approach

This application connects the user with the Machine Learning Model throught an endpoint, having in mind a two-way flow of information: 
- The user types a movie review in the  web application
- The application sends this information to the model
- The model gathers and processes the information and generate a forecast
- The forecast (output) is given to the user

## The model and data

This Model is based on a recurrent neural network for the purpose of detemining the sentiment of a movie review using [IMDB data set](http://ai.stanford.edu/~amaas/data/sentiment/). A set of 25,000 highly polar movie reviews for training, and 25,000 for testing, raw text and also processed bag of words formats.

# Steps

1. Create a notebook instance in the SageMaker environment.

2. Train the model was done with a virtual machine ml.p2.xlarge (1 GPU, 4 vCPU and 61 GiB RAM).

3. Deploy the model and application was done with a virtual machine ml.m4.xlarge (4 CPU virtual, 16 GiB,) US$0.24 per hour.

4. For this step you need a modification in your limits in the AWS support center, creating a case, service limit increase, limit type SageMaker and only 1 instance in the limit by the region you've selected.

5. Downloading the data

6. Preparing and Processing the data
    - Transform the data
    - Save word_dict
    - Transform the reviews
    
7. Upload the data to S3
    - Save the processed training dataset locally
    - Uploading the training dataset
    
8. Build and train the PyTorch Model
    - The trining method
    - Training the model

9. Testing the model

11. Deploy the model for testing

12. Use the model for testing
    - More testing
    - Delete the endpoint

12. Deploy the model for the web app
    - Writing inference code
    - Deploying the model
    - Testing the model

13. Use the model for the web app
    - App -> API -> Lambda -> Model
    - Setting up a Lambda function
    - Setting up API Gateway

14. Deploying the web app

15. Delete the endpoint

# Sources

Database:
@InProceedings{maas-EtAl:2011:ACL-HLT2011,
  author    = {Maas, Andrew L.  and  Daly, Raymond E.  and  Pham, Peter T.  and  Huang, Dan  and  Ng, Andrew Y.  and  Potts, Christopher},
  title     = {Learning Word Vectors for Sentiment Analysis},
  booktitle = {Proceedings of the 49th Annual Meeting of the Association for Computational Linguistics: Human Language Technologies},
  month     = {June},
  year      = {2011},
  address   = {Portland, Oregon, USA},
  publisher = {Association for Computational Linguistics},
  pages     = {142--150},
  url       = {http://www.aclweb.org/anthology/P11-1015}
}

### Libraries:
- [PyTorch](https://pytorch.org/)
- [BeautifulSoup](https://pypi.org/project/beautifulsoup4/)

### Cloud Computing
- [Amazon Web Services (AWS)](https://aws.amazon.com/es/)
- [AWS SageMaker](https://aws.amazon.com/es/sagemaker/)
- [AWS Lambda](https://aws.amazon.com/es/lambda/)
- [AWS API GATEWAY](https://aws.amazon.com/es/api-gateway/)
