# Python-Flask-App-Deployment-Using-AWS-Elastic-Beanstalk

## Project Overview

This project demonstrates the process of building a simple Python Flask application and deploying it using AWS Elastic Beanstalk. AWS Elastic Beanstalk simplifies the deployment, management, and scaling of web applications. By following this guide, you'll be able to deploy your Flask application and manage it through the AWS Management Console.

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Procedure](#procedure)
    1. [Step 1: Develop a Simple Python Flask Application](#step-1-develop-a-simple-python-flask-application)
    2. [Step 2: Install the AWS Elastic Beanstalk CLI and Initialize the Environment](#step-2-install-the-aws-elastic-beanstalk-cli-and-initialize-the-environment)
    3. [Step 3: Deploy the Flask Application Using Elastic Beanstalk](#step-3-deploy-the-flask-application-using-elastic-beanstalk)
    4. [Step 4: Monitor and Scale the Application Using the AWS Management Console](#step-4-monitor-and-scale-the-application-using-the-aws-management-console)
4. [Conclusion](#conclusion)
5. [Acknowledgments](#acknowledgments)

## Introduction

This guide will walk you through the process of deploying a Python Flask application on AWS Elastic Beanstalk, a fully managed service that allows you to easily deploy and manage applications in the cloud without worrying about the infrastructure.

## Prerequisites

Before you begin, ensure that you have the following:

- Python installed on your local machine.
- AWS CLI installed and configured with your AWS credentials.
- AWS Elastic Beanstalk CLI installed.
- Basic understanding of Python and Flask.

## Procedure

### Step 1: Develop a Simple Python Flask Application

1. **Create a new directory for your project**:
    ```bash
    mkdir flask-app
    cd flask-app
    ```

2. **Set up a virtual environment**:
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install Flask**:
    ```bash
    pip install Flask
    ```

4. **Create a simple Flask application**:
    Create a file named `app.py` and add the following code:
    ```python
    from flask import Flask

    app = Flask(__name__)

    @app.route('/')
    def hello_world():
        return 'Hello, World!'

    if __name__ == '__main__':
        app.run(debug=True)
    ```

5. **Test the application locally**:
    ```bash
    python app.py
    ```
    Visit `http://127.0.0.1:5000/` in your browser to see the application running.

### Step 2: Install the AWS Elastic Beanstalk CLI and Initialize the Environment

1. **Install the AWS Elastic Beanstalk CLI**:
    Follow the instructions from the [official AWS documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) to install the Elastic Beanstalk CLI.

2. **Initialize your Elastic Beanstalk environment**:
    ```bash
    eb init -p python-3.x flask-app
    ```
    - Select your AWS region.
    - Choose an existing keypair if available, or create a new one.

3. **Create an Elastic Beanstalk environment**:
    ```bash
    eb create flask-env
    ```

### Step 3: Deploy the Flask Application Using Elastic Beanstalk

1. **Deploy your application**:
    ```bash
    eb deploy
    ```

2. **Access your deployed application**:
    After deployment, Elastic Beanstalk will provide a URL where your application is running. You can access your Flask application via this URL.

### Step 4: Monitor and Scale the Application Using the AWS Management Console

1. **Monitor the application's performance**:
    - Log in to the [AWS Management Console](https://aws.amazon.com/console/).
    - Navigate to the Elastic Beanstalk service.
    - Select your application to view its health, logs, and monitoring metrics.

2. **Scale the application**:
    - In the Elastic Beanstalk environment, you can adjust the scaling settings to handle increased traffic. 
    - Configure auto-scaling based on the application's needs.

## Conclusion

By following this guide,we can successfully deployed a Python Flask application using AWS Elastic Beanstalk. This process showcases how easy it is to manage and scale web applications using AWS services.

## Acknowledgments

I would like to thank my mentors and ChatGPT, and the AWS community for their support and guidance throughout this project. Their contributions have been invaluable in the successful completion of this deployment process.
