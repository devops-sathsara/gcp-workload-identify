# GCP Identity Federation for GitHub Actions with Terraform


*This repository contains Terraform scripts that enable you to set up Identity Federation between GitHub Actions and Google Cloud Platform (GCP). By leveraging GitHub Actions and GCP Identity Federation, you can seamlessly integrate your GitHub workflows with GCP resources, allowing secure and automated deployments.*


## Introduction
Identity Federation for GitHub Actions allows you to authenticate and authorize GitHub Actions workflows to interact with your GCP resources. This integration ensures that only trusted actions and workflows can access your sensitive GCP infrastructure.

This repository provides a Terraform configuration that sets up the necessary resources in your GCP project, including service accounts, roles, and policies, to enable Identity Federation for GitHub Actions.


## Features
* __Automated Setup__: The Terraform script in this repository automates the process of configuring Identity Federation for GitHub Actions on GCP, saving you time and effort.
* __Secure Communication__: GitHub Actions securely interacts with your GCP infrastructure by leveraging Identity Federation, ensuring your sensitive resources remain protected.
* __Fine-Grained Access Control__: You can easily define the roles and permissions for GitHub Actions to access specific GCP resources, granting only the necessary privileges.
* __Continuous Integration/Deployment (CI/CD)__: With Identity Federation enabled, you can seamlessly incorporate GitHub Actions workflows into your CI/CD pipeline, allowing for efficient and automated deployments.


## Prerequisites
Before using the Terraform scripts in this repository, ensure you have the following:

* A Google Cloud Platform (GCP) account.
* Appropriate permissions to create resources in the GCP account.
* Terraform installed on your local machine.



##  Getting Started
To get started, follow these steps:

1. Create a new GCP projects for each environment

```
PROJECT_ID=<project_id>
gcloud projects create $PROJECT_ID
```


2. Link GCP project to the billing account

```
gcloud alpha billing accounts projects link $PROJECT_ID --billing-account=0X0X0X-0X0X0X-0X0X0X
```


3. Set up gcloud CLI for the new GCP project

```
gcloud auth application-default login --project $PROJECT_ID
gcloud config set project $PROJECT_ID
```


4. Create a GCS bucket for Terraform backend

```
gcloud storage buckets create gs://<bucket-name> --project $PROJECT_ID --location <bucket-location>
```


## Contribution
Contributions are welcome! If you encounter any issues, have ideas for improvements, or would like to add new features, please submit a pull request. Make sure to follow the existing coding style and provide clear commit messages.


## Resources
[GitHub Actions Documentation](https://docs.github.com/en/actions)
[Google Cloud Platform Documentation](https://cloud.google.com/docs)
[Terraform Documentation](https://developer.hashicorp.com/terraform/docs)
