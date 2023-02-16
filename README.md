[![CircleCI](https://dl.circleci.com/status-badge/img/gh/king-tobi/project4/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/king-tobi/project4/tree/main)

## Project Overview

In this project, i applied the skills i acquired in this Section to operationalize a Machine Learning Microservice API. 

The following are the steps and procedures  i took in the course of this project.

I was given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, 
such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, 
which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tested my
ability to operationalize a Python flask-app in a provided file, `app.py`—that serves out predictions (inference) about housing prices 
through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

The project goal was to operationalize this workine machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source 
system for automating the management of containerized applications. In this project I:
* Tested my project code using linting
* Completed a Dockerfile to containerize this application
* Deployed my containerized application using Docker and made a prediction
* Improved the log statements in the source code for this application
* Configured Kubernetes and created a Kubernetes cluster
* Deployed a container using Kubernetes and made a prediction
* Uploaded a complete Github repo with CircleCI to indicate that my code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase my abilities to operationalize production microservices.**

---

## Setup the Environment

* I Created a virtual env with Python 3.7 and activated it. 
* 
	python3 -m venv ~/.devops
source .devops/bin/activate
I Ran `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

    
Task 1: I Completed the Dockerfile

       After completing this file and saved it, i went back to the terminal and ran "make lint" again to see if hadolint 
        catches any errors in your Dockerfile
        

Task 2: I Ran a Container & Made a Prediction:
        I built and ran the docker image that i defined in the Dockerfile, 
        and then i was able to test my application locally by having the containerized application accept some 
        input data and produce a prediction about housing prices. run_docker.sh
        
Task 3: I Improved the Logging & Saved the Output.
        Logging is an important part of debugging and understandability. Many times, logs will be how engineers 
        figure out what an app is doing as it processes some input. In this case, iupdated the app.py code,
        saved it and rann ./run_docker.sh again and made the same prediction in a separate terminal window, 
        i then saved the output text into docker_out.txt


        
                
Task 4: I Uploaded the Docker Image:
        Now that i’ve tested my containerized image locally, then i uploaded my built image to docker. This will make
        it accessible to a Kubernets cluster.
        
       
Task 5: I Configured Kubernetes to Run Locally
        Since i have a virtual machine like minikube installed, as per the project environmet instructions. To start a local cluster,
        i typed the terminal command: minikube start
        
        After minikube started, a cluster was running locally. Then i checked that i had one cluster running by typing kubectl config
        view where i saw one cluster with a certificate-authority and server.

Task 6: I Deployed with Kubernetes and Saved Output Logs
        Now that i’ve uploaded the docker image and configured Kubernetes and had a cluster running,i waas able to deploy my application on the 
        Kubernetes cluster. This involves running my containerized application using kubectl, which is a command line interface for interacting with 
        Kubernetes clusters. I called the script run_kubernetes.sh, After, i've called the run_kubernetes.sh, and ii had a pod up and running, i made 
         a prediction using a separate terminal tab, and a call to ./make_prediction.sh ad copied the output text into docker_out.txt.
         
Task 7: I Deleted the Cluster:
        After i was done deploying my containerized application and making test predictions via Kubernetes cluster, then cleaned up my resources and deleted
        the kubernetes cluster with a call to minikube delete.
        
Task 8: CircleCI Integration:
        CircleCI is a tool that defines an automated testing environment; getting a CircleCI badge that reads "Passed" on a repository indicates that the 
        project code has passed all lint tests. CircleCI uses a YAML file to identify how you want your testing environment set up and what tests you want to run.
        On CircleCI 2.0, this file must be called config.yml and must be in a hidden folder called .circleci. On Mac, Linux, and Windows systems, files and folders
        whose names start with a period are treated as system files that are hidden from users by default.
        To create the file and folder on GitHub, I clicked on the Create new file button on the repo page and type .circleci/config.yml. 
        i wrote the required yaml code to carry out the build on circleci, i configured my circleci wiith my github repo and clicked "start build"
        After the build was successful i then added a status badge indicating that my project has "Passed" CircleCI tests,



