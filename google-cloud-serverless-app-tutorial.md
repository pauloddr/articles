# Google Cloud Serverless App Tutorial

Publishing a functional web application in Google Cloud Platform (GCP), from zero to hero, at virtually no cost.

## Requirements

* a domain name
* a Google account
* a valid credit card

## Languages and Frameworks

* HTML
* Javascript/Node
* Angular

## Introduction

This guide describes how to create a very basic (but functional) web application in the Google Cloud Platform without the need of deploying any servers.

The following tasks will be covered in detail:

* Setting up the domain;
* Creating a Google Cloud Project;
* Creating and configuring a new Google Storage Bucket to host the static website (frontend);
* Creating the HTMLs and configuring Angular 1.x;
* Creating a new Google Cloud Function;
* Calling the Google Function from the frontend;
* Learning about Google Datastore;
* Changing our function to access Datastore records.
* Next steps and improvements.

### Why a credit card?

Google does not allow the activation of certain services without a Billing Account with a valid payment method. We will be working with two services (Google Cloud Storage and Google Cloud Functions) that require Billing to be active.

You are only charged, however, for the amount you use. Additionally, there's an "Always Free" tier in GCP which allows your function to be called 2 million times per month without charges. It also includes a fairly high amount of hits that your Google Storage Bucket objects can take in order for any charge to begin. So, for small applications, you will very likely run things for free.

### Why a domain name?

Without a domain name, you will be unable to create a "website bucket", which has extended functionality over normal buckets. Website buckets allow redirecting of 404 requests (when a page is not found) to another HTML file of your choice. This will be essential for web applications that use routing in HTML5 mode, which Angular supports.

## Getting Started

Before we can work on the GCP console, it's useful to set up the domain first, just so the DNS propagation takes place while we work in other stuff.

(TODO)

### Creating a new GCP Project

The Google Cloud Platform console can be accessed via https://console.cloud.google.com/. Create a Google account if you don't have one yet. 

After logging in, create a Billing Account and add your credit card as a payment options. Instructions can be found [here](https://support.google.com/cloud/answer/6288653?hl=en). After that, we're ready to create a project.

Creating a project may seem trivial at first, but there is one aspect you should be aware of: the __project ID__.

GCP will use your project ID as part of a number of things. To name one, they will be part of the URL of all your Google Functions.

So choosing a unique project ID (without random numbers) is a good way to make your URLs easier to work with.

However, if you're creating a project that you intend to delete later, then it's highly recommended you create an ID with random numbers. At the time of this writing, IDs of deleted projects cannot be reused, so (for now) do not delete a project  if you want to keep its ID.

After you decide what kind of project you're working with, go ahead and create it. Creating a project has no cost.

Next, we will create a static website using a Google Storage bucket.

### Creating a Static Website

After creating your project, go to the Side Menu and select __Storage__, and then __Create Bucket__.

GCP requires that the bucket name is unique in the Google universe. So a good convention is to use a full qualified domain name -- even if it doesn't exist -- replacing the dots with dashes.

Examples:

* `logs-mywebsite-com`
* `dev-mywebsite-com`

If you don't have a domain name, you can access your static website through a public bucket URL that GCP provides. (If you _do_ have a domain name, see the Appendix for instructions.)

For the bucket region, you can choose:

* __Regional__: when you want your static website to be easily publishable. It won't be available from multiple servers across the region, but if you're just testing stuff or working on a dev site, this is the recommended region.
* __Multi-Regional__: when you want your static website to be highly available. But it can be more troublesome to publish new versions, as it can take time for all servers to pick up your changes.

Both regions offer no real difference in pricing, for the amount of hits we're working with. This becomes more of an issue for large applications with high traffic.

After creating the bucket, create a `index.html` file in your computer with any content, then upload it to the bucket using the GCP interface.

After the file finishes uploading, check the __Share publicly__ option in the list.

-WIP-
