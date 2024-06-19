# Hosting a simple website on AWS s3

## Overview

This is a brief description of how to host a simple website on AWS Simple Storage Service. 

## Prerequisites

Make sure you have the following prerequisites;

- [AWS Account setup](https://console.aws.amazon.com/console/home)

## How to Host a simple website on s3

- **Sign in to AWS Console**

Using your AWS account credentials (username and password), log into the AWS Management Console.

![Signing into AWS Management Console](./images/web01.png)

- **Create an S3 bucket**

On the management console, search for s3 and click on the _Create Bucket_ buttton. 

![Search for S3](./images/web02.png)
![Create bucket button](./images/web03.png)

Specify a unique name for your bucket

![bucket name](./images/web04.png)

Enable the ACLs and uncheck the box to _Block all public access_

![acls](./images/web05.png)
![block access](./images/web06.png)

You can optionally enable versioning and create tags

![versioning-tags](./images/web07.png)

Select the encryption type (Server-side encryption, SSE with AWS KMS)

![encryption](./images/web08.png)

You can decide to enable Object Lock to lock the object to prevent it from accidental deletion or overwrite. Enabling Object Lock automatically enables Versioning.

![object-lock](./images/web09.png)

Your Bucket is created successfully

![create-bucket](./images/web10.png)

- **Configure Bucket Properties**

- Select your bucket from the list of buckets and scroll all the way to static web hosting, then click on the _Edit_ button.

![select bucket](./images/web11.png)
![web-hosting](./images/web12.png)

- Enable static web hosting, then specify the index file and click on the _Save changes_ button.
![web-hosting](./images/web13.png)

- Go back to the _Objects_ tab and click on Upload

![upload](./images/web14.png)

- Upload the folder containing the files for the website

![upload-folder](./images/web15.png)

- Go back to the Properties tab and scroll down to static web hosting. A website url link would be provided. The link would direct users to your website.

![url-link](./images/web17.png)

## Website URL

Here is the link to the deployed website on AWS s3

![AWS s3 Deployed URL](http://perpetual-aws-bucket.s3-website-us-west-2.amazonaws.com/)

## _Thank you for reading_

