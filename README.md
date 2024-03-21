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

- <b>VsCode</b>

- <b>AWS Cloud9</b>

- <b>AWS Codecommit</b>

- <b>AWS Codebuilt</b>

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

- <b> First, go on Aws Cloudformation we test our template by deploying it to make sure it works
<br />


<img src="https://i.imgur.com/P0rc8GA.png" height="80%" width="80%" alt="Testing our CFN Template"/>

<img src="https://i.imgur.com/EPUWkfi.png" height="80%" width="80%" alt="Testing our CFN Template"/>



<br />


- <b> Once bucket is created, upload "index.html" file


<img src="https://i.imgur.com/8sYqRJh.png" height="80%" width="80%" alt="Create static website steps"/>
</p>
<br />
<br />




- <b> Under "Properties", scroll all the way down and enable hosting a static website
<br />
<br />



- <b> In the same setting where it says "Index document", put the name of the index.html file that was just uploaded and save changes


<img src="https://i.imgur.com/ptszXKq.png" height="80%" width="80%" alt="Create static website steps"/>
<br />
<br />



- <b> Under "Permission", edit the s3 policy bucket to give permission/access to bucket
<br />
<br />


- <b> Bucket should now be public:



<img src="https://i.imgur.com/yZTe3Oi.png" height="80%" width="80%" alt="Create static website steps"/>
<br />
<br />



- <b> On route 53 purchase the domain name of the website you are trying to create 
<br />
<br />


- <b> < Or if already have a registered domaine make sure subdomain match the bucket name you are using to create the static website >
<br />
<br />




- <b> Next create a record and select Alias. choose "Alias to S3 website endpoint" and select the region associated to the bucket:

<img src="https://i.imgur.com/PHVWWr6.png" height="80%" width="80%" alt="Create static website steps"/>
<br />
<br />


- <b> Test it:



<img src="https://i.imgur.com/GGs7oET.png" height="80%" width="80%" alt="Create static website steps"/>
<br />
<br />



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
