# CircleCI and GKE
How to deploy Kubernetes manifests on GKE Cluster from Circle CI.

## Prerequisites
* Create a service account on GCP to allow deploying to GKE
* Connect Github repository to Circle CI

## Configuration
Configuration of a new repository to Circle CI steps in 2 times :
* Generate self repository configuration in `.circleci/config.yml`
* Create environment variables of Circle CI workflow

### Step 1 : Generate configuraiton file

### Step 2 : Create environment variables
To allow Circle CI to connect to GCP GKE you need to provides credentials to Circle CI. You must NOT set it in you configuration file not to expose it to whole world.

Go into your workflow > settings and set the following environment variables :
* `GCLOUD_SERVICE_KEY`: Content of the private key generated for the service account
* `GOOGLE_PROJECT_ID`: Name of the GCP Project
* `GOOGLE_CLUSTER_NAME`: Name of the GKE Cluster
* `GOOGLE_COMPUTE_ZONE`: Zone of the GKE Cluster
