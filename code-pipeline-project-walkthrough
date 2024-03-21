# Deploying a Cloudformation Template using codepipeline in the us east 1 Region


This project consist in deploying a Cloudformation template using Aws service Codepipeline. For this project we have a Cloudformation template ready to deploy

In this project we will have 3 stages
- The source phase
- The build phase
- The deploy phase

On the source stage we will be using Aws service Codecommit that will host our cfn template and buildspec.yml file that we pushed from our local environment

The cloudformation is a template to deploy an Ec2 server 

We will be writing a buildspec.yaml file based on our use case and that will be used to create the build artifact

The build stage will consist on testing the cfn template and creating an artifact that will be used on the deploy phase to help us deploy our template

On s3 we will create a bucket to use to package the artifact created at the build stage

The cfn templte will be then deployed to Cloudformation

The deploy stage will be set up as is:
- A stage deploy in the us-west-3 (paris) region
- An approval stage
- A deploy to us-east-1 (n.virginia) region
