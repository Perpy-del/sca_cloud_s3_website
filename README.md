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

[AWS s3 Deployed URL](http://perpetual-aws-bucket.s3-website-us-west-2.amazonaws.com/)

![Website Screenshot](./images/web18.png)


## Using AWS CloudFront to deliver content for low-latency

For this purpose of this presentation, I would be using the AWS Management Console, but you can also use _AWS SDKs_, _CloudFront API_, _AWS CLI_, and _Windows PowerShell tool_

- Search for CloudFront from Services tab on the AWS Management Console
![cloudfront-service](./images/web19.png)

- Click on the _Create a CloudFront distribution_ button. At this time, you must have created an s3 bucket and hosted your website as discussed in the previous topics. [Hosting a website on S3](https://github.com/Perpy-del/sca_cloud_s3_website?tab=readme-ov-file#how-to-host-a-simple-website-on-s3)

![cloudfront-distribution](./images/web20.png)

- For Origin, Origin domain, choose the S3 bucket that you created
![origin-domain](./images/web21.png)

- For Web Application Firewall (WAF), select one of the options. The _Enable Security settings_ will cost you. Selecting the other cost you nothing.
![WAF](./images/web22.png)
![WAF](./images/web23.png)

- For all other sections and settings, accept the default values. Then choose _Create distribution_
![create](./images/web24.png)
![create](./images/web25.png)

- When your distribution is done deploying, the Last modified field changes from Deploying to a date and time.
![deploy](./images/web26.png)

- Record the domain name that CloudFront assigns to your distribution. It looks similar to the following: d111111abcdef8.cloudfront.net.
![domain-cloudfront](./images/web27.png)

## CloudFront Website URL

Here is the link to the deployed website on AWS CloudFront

[AWS CloudFront URL](https://d2ma1n9qaokle.cloudfront.net/)

![Website Screenshot](./images/web28.png)

It looks just the same as the deployed s3 bucket website but this is the cached version and it reduces latency.



## _Thank you for reading_

