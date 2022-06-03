
## Upload your Docker image to Amazon Registry

- Create a repository dashboard in ECR (the AWS Elastic Container Registry). 
- Create an access key for your AWS account
- Enable the Docker client to authenticate to the AWS registry
- Push docker image into the dashboard repository

### Configure your aws cli

    aws configure set aws_access_key_id <YOUR_ACCESS_KEY>
    aws configure set aws_secret_access_key <YOUR_SECRET_KEY>
    aws configure set default.region <YOUR_REGION>
    aws configure set default.output json

### Login to ECR:

    aws ecr get-login-password | docker login --username AWS --password-stdin ####.dkr.ecr.us-east-1.amazonaws.com

### Push the built dashboard into the AWS repository

    docker tag image name <ACCOUNT NUM>.dkr.ecr.<REGION>.amazonaws.com/ECR_repo
  
    docker push <ACCOUNT NUM>.dkr.ecr.<REGION>.amazonaws.com/ECR_repo


### Deploy the Docker Container using ECS

#### Accessing the Dashboard Service

   - Edit the Inbound Rules
