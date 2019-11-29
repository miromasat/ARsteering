# ARsteering
Content for AUT401 - Building AR and AI automotive owner applications with AWS

## Abstract
Augmented reality (AR), AI, and IoT services can be used to jointly create both visual and aural owner applications, such as an interactive owner’s manual. This session is dedicated to selecting and applying the appropriate AWS tools and services to build interactive owner applications for increasing after-market sales, personalization/localization of services, next-generation design, advertising, and media distribution. Developers and UX designers learn how to easily create applications that reinvent the way we interact with our vehicles in both the physical and digital worlds. Please bring your laptop.

## Architecture Diagram
![Architecture of ARsteering](./arch.png)

## Step 1 (deploying CloudFormation template)
Clicking a button below (and following a wizard), deploy `AWS CloudFormation` stack into your account and `us-east-1` region. 
This stack deploys:
* `Amazon Cognito` identity pool (and associated `AWS IAM` role), that allows `Amazon Sumerian` scene to talk to other services
* `Amazon DynamoDB` table, that will contain manual functions, their steps and descriptions, we want to support. (one initial function for geashift/shifter will be already stored in this table)
* `AWS Lambda` function (and associated `AWS IAM` role) that helps `Amazon Lex` bot access `Amazon DynamoDB` table

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=buildkite&templateURL=https://s3.amazonaws.com/my-great-stack.json)

## Step 2 (importing Lex bot)
Download `AWS Lex` [package into your computer from here](https://www.google.com). Navigate to `AWS Lex` service in `us-east-1` region, import the zip file that you've downloaded. You will now see `ARsteering` bot in your console. At the bottom of a page of particular intent, link the intent to `AWS Lambda` function called `ARsteering`, that was provisioned by cloudformation in Step 1. Build the bot, test it and publish them under the alias `latest`.

## Step 3 (importing Sumerian scene)
### Setting up Cognito
### Setting up Lex
### Changing accent colors and highlight colors

## Step 4 (adding another commands)

## Step 5 (deployment options)