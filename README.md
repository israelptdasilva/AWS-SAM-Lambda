# AWS SAM Lambda Function

*© Israel Pereira Tavares da Silva*

> The AWS Serverless Application Model (SAM) is an open-source framework for building serverless applications. It provides shorthand syntax to express functions, APIs, databases, and event source mappings. With just a few lines per resource, you can define the application you want and model it using YAML. During deployment, SAM transforms and expands the SAM syntax into AWS CloudFormation syntax, enabling you to build serverless applications faster.

* [SAM](https://aws.amazon.com/serverless/sam/)
* [Lambda](https://aws.amazon.com/lambda/)

### Setup

Clone the project:

```bash
> git clone https://github.com/israelptdasilva/AWS-SAM-Lambda
> cd AWS-SAM-Lambda
```

#### Conda
You may want to use [conda](https://docs.conda.io/en/latest/miniconda.html) or another environment manager to have a separate environment to install `awscli` and `aws-sam-cli`. 

```bash
> conda create -n lambda
> conda activate lambda
> conda install -c conda-forge awscli
> pip install aws-sam-cli
```
After installing `awscli` and `aws-sam-cli` you'll need to [configure](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) `awscli` with your access keys:

```bash
> aws configure
```

#### Docker

It is necessay to have [Docker](https://docs.docker.com) installed if you want o test the lambda function locally.

### Basic SAM Usage
#### Run Locally

Executing the command bellow builds a docker image (golang) in which the function will be ran in.

```bash
> sam local invoke GoLambdaFunction -e event.json
```

#### Validate & Deploy

A successfull deploy will create a S3 bucket with the lambda function, the lambda function itself, a cloudformation stack and the necessay roles.

```bash
> sam validate
> sam build
> sam deploy --guided (or just sam deploy)
```

#### Delete Stack

Delete the deployed stack if you don't want to keep it around anymore.

```bash
> sam delete
```

> Quem florestas e mares foi rasgando
e entre raios, pedradas e metralhas,
ficou gemendo, mas ficou sonhando! (João da Cruz e Sousa)
