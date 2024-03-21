# Deploying a Cloudformation Template with AWS codepipeline in the us-east-1 Region





<h2>Description</h2>
This project consist in deploying a Cloudformation template using Aws service Codepipeline. For this project we have a Cloudformation template ready to deploy

In this project we will have 3 stages
- The source phase
- The build phase
- The deploy phase
<br />
<br />
<br />



<h2>Services Used </h2>


- <b>AWS Cloud9</b>

- <b>AWS Codecommit</b>

- <b>AWS Codebuild</b>

- <b>Aws Cloudformation</b>

- <b>AWS S3</b>

- <b>AWS IAM </b> 
<br />



<h2>Program walk-through:</h2>

<p align="center">

 <br />

- <b> We have a Cloudformation template to deploy an Ec2 instance in us-east 1 <br/>
<br />
<br />

- <b> First, go on Aws Cloudformation test the template by deploying it to make sure it works
<br />


<img src="https://i.imgur.com/P0rc8GA.png" height="80%" width="80%" alt="Testing our CFN Template"/>

<img src="https://i.imgur.com/EPUWkfi.png" height="80%" width="80%" alt="Testing our CFN Template"/>





<br />
<br />




 <b> Setup the test environment
- Using Aws Cloud9, create a testing environment by deploying an ec2 instance and connect to it
- Define your requirement such as instance type, Network setting

  <img src="https://i.imgur.com/ZKkjw9D.png" height="80%" width="80%" alt="Create static website steps"/>




<br />
<br />

Once created, connect to the instance 

Using the terminal, check for CLI access using command aws --version

Create a folder that will contain your code/cfn template and cd into it

 <img src="https://i.imgur.com/bljygUM.png" height="80%" width="80%" alt="Create static website steps"/>


<br />
<br />


in the new folder upload the template

Create a file and upload your template


<br />
<br />

The new file created, test the file with a cfn-lint

first verify the version of python using command python3 --version

install cfn-lint using command "pip install cfn-lint"

 <img src="https://i.imgur.com/Wfn3XAj.png" height="80%" width="80%" alt="Create static website steps"/>






</p>
<br />
<br />




- <b> Test the file with cfn-lint installed using the command: cfn-lint < name of the file >

If there's no return, it means your template do not contain any error and your are good for the next step


 <img src="https://i.imgur.com/bUzT46f.png" height="80%" width="80%" alt="Create static website steps"/>
 
<br />
<br />



- <b> On Aws Codecommit, create a repository for the source stage of the pipeline


<img src="https://i.imgur.com/TpTiC7F.png" height="80%" width="80%" alt="Create static website steps"/>
<br />
<br />

- <b> Clone the repository and cd into it
- Copy the file in the repo
- stage the file, use the command git commit -m"" to commit, push the file


<img src="https://i.imgur.com/magndO8.png" height="80%" width="80%" alt="Create static website steps"/>
  

<img src="https://i.imgur.com/j2kxxoi.png" height="80%" width="80%" alt="Create static website steps"/>
   
  


<br />

<br />



- <b> On Codepipeline create a pipeline
<br />
<br />


- <b> Choose the source stage
  in this case Codecommit is the source



<img src="https://i.imgur.com/8KNEYPz.png" height="80%" width="80%" alt="Create static website steps"/>
<br />
<br />

<img src="https://i.imgur.com/GF18jlK.png" height="80%" width="80%" alt="Create static website steps"/>

<br />

<br />


- <b> Add a build stage
<br />

<img src="https://i.imgur.com/a4Ug7NM.png" height="80%" width="80%" alt="Create static website steps"/>
<br />


- <b> < For Project name select create project

  Select the environment to work with

  Under buildspec setting select: Use a buildspec file
<br />
<br />

<img src="https://i.imgur.com/R05b0SU.png" height="80%" width="80%" alt="Create static website steps"/>

<br />

<img src="https://i.imgur.com/e91mk2S.png" height="80%" width="80%" alt="Create static website steps"/>

<br />

<img src="https://i.imgur.com/acA6K82.png" height="80%" width="80%" alt="Create static website steps"/>






- <b> Add a deploy stage

setup the deploy stage by choosing the deploy provider. in this case Cloudformation

our test deploy stage Region is eu-west-3 (Paris)

Under Template
select Artifact name and define the name as the file artifact template created (that will be created on s3) 

<img src="https://i.imgur.com/PHVWWr6.png" height="80%" width="80%" alt="Create static website steps"/>
<br />
<br />

Define IAM role

Define output file name

Review and Create Pipeline


At this point the pipeline must have failed because of missing elements


- <b> Creating the buildspec file

On S3 create a bucket to host the cloudformation package artificat needed to advance on the build stage
  Based on requierements, create buildspec as a yaml file
  on Aws cloud9 create buildspec.yaml file and push to Aws codecommit



<img src="https://i.imgur.com/GGs7oET.png" height="80%" width="80%" alt="Create static website steps"/>
<br />
<br />

- <b> Deploy stage

- First deployment to Paris region

  make sure to fix all overwrite settings

  release changes



  Approve the 
- <b> Create image of the instance and test it





<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
