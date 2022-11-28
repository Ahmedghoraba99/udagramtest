# Hosting a Full-Stack Application

## Third project egFWD fullstack nanod degree

---

# Udagram

project linl:
http://mylongbucketname666596.s3-website-us-east-1.amazonaws.com

## Archetichture Overview

![Alt text](/Screenshots/Diagram.PNG?raw=true "Title")

### AWS configuration

Provision the necessary AWS services needed for running the application:

#### S3 bucket

1. Create IAM user using your AWS account and give it admin premission

2. Using AWS CLI Create s3 bucket using command

3. In AWS, provision a s3 bucket for hosting the uploaded files. using command:

```c

$ aws s3 mb s3://YourBucketName

```

4. configure your bucket to allow public access and change the bucket policy to the following : AND make sure ACL is enabled

```json
{
  "Version": "2012-10-17",

  "Statement": [
    {
      "Sid": "PublicReadGetObject",

      "Effect": "Allow",

      "Principal": "*",

      "Action": [
        "s3:PutObject",

        "s3:PutObjectAcl",

        "s3:GetObject",

        "s3:GetObjectAcl",

        "s3:AbortMultipartUpload"
      ],

      "Resource": "arn:aws:s3:::YourBucketName/*"
    }
  ]
}
```

#### RDS

1. Create RDS database
2. Choose the type POSTGRESQL
3. make sure to edit the inbound rules of your DB to allow connection from different IP's

---

#### ElasticBeanstalk

1. using elastic beanstalk create node.JS environment using the standard settings

---

### Locally running the project

> you will need to reconfigure some of the files like the api url & env
> variables to run this on your local machine
> and modify the scripts in package.json in both files

#### Installing dependencies:

1. in the `root` folder open a terminal and run the following commands:

```
$ npm run frontend:install
$ npm run api:install
```

#### Running backend and frontend

This should be done in two seperate terminals...
$ npm run start
$ cd udagram-frontend && npm run start

## Screenshots

AWS:
![Alt text](/Screenshots/RDS%20status.png?raw=true "Title")
![Alt text](/Screenshots/s3%20status.png?raw=true "Title")
![Alt text](/Screenshots/EB%20status.png?raw=true "Title")
CrcleCI:
![Alt text](/Screenshots/circleci%20env1.png?raw=true "Title")
![Alt text](/Screenshots/circleci%20env2.png?raw=true "Title")
![Alt text](/Screenshots/CirclCi%20pipeline.png?raw=true "Title")

## Testing

This project contains two different test suite: unit tests and End-To-End tests(e2e). Follow these steps to run the tests.

1.  `cd starter/udagram-frontend`

1.  `npm run test`

1.  `npm run e2e`

There are no Unit test on the back-end

### Unit Tests:

Unit tests are using the Jasmine Framework.

### End to End Tests:

The e2e tests are using Protractor and Jasmine.

## Built With

- [Angular](https://angular.io/) - Single Page Application Framework

- [Node](https://nodejs.org) - Javascript Runtime

- [Express](https://expressjs.com/) - Javascript API Framework

## License

[License](LICENSE.txt)
