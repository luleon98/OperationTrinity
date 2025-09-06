# Grocery Checklist Project

## Overview
The Grocery Checklist is a web-based app to add, track, update, and delete grocery items. I built this to organize my grocery needs and as an alternative to the default Notes app on my iPhone. This project is fully hosted on AWS and leverages multiple services including DynamoDB, Lambda, API Gateway, Amplify, and IAM. The architecture demonstrates serverless CRUD operations in a production-like environment.

## Live Preview
* [Live Site](https://dev.d3h7hp93k3ddbs.amplifyapp.com)

## Visual Preview
* [Webb View](
* [Mobile View](

## Architecture
The app follows a serverless architecture: [Diagram](checklist-diagram.png)
* DynamoDB → stores grocery items (userId as partition key, itemId as sort key)
* Lambda functions → implement Create, Read, Update, Delete operations
* API Gateway → exposes Lambda functions via RESTful HTTP endpoints
* Amplify → hosts the frontend and connects to API Gateway
* IAM roles → provide least privilege access for each Lambda function

## Tech Stack
* AWS Services: DynamoDB, Lambda, IAM, API Gateway, Amplify
* Languages: JavaScript (Node.js)
* Tools/Frameworks: AWS Console, Postman

## Deployment / Setup
* DynamoDB Table
  * Create a table with userId (string) as partition key and itemId (string) as sort key
  * Add attributes: name (string), quantity (number), checked (boolean)
* Lambda Functions
  * Create four functions for CRUD: createItem, getItems, updateItem, deleteItem
  * Implement input validation and error handling (400 / 500 status codes)
* IAM Roles
  * Assign least-privilege permissions to each Lambda for their respective DynamoDB operations
  * Include CloudWatch logging
* API Gateway Integration
  * Connect each Lambda to an HTTP API route
  * Deploy API and test endpoints via Postman
* Frontend Deployment
  * Create index.html with JavaScript for fetching and updating items
  * Package as a ZIP and deploy to AWS Amplify
  * Configure CORS in API Gateway to allow requests from the Amplify domain
  * After deployment, the full CRUD flow is operational via the website

## Features & Learning
* Designed and implemented a serverless backend on AWS
* Learned DynamoDB operations: PutItem, Query, UpdateItem, DeleteItem
* Learned Lambda integration with API Gateway and frontend
* Configured IAM least privilege for Lambda security
* Deployed a static website with AWS Amplify

## Future Improvements
* Integrate Cognito authentication for multi-user support
* Add categories or sorting/filtering for grocery items
* Implement dynamic frontend framework (React/Next.js) for richer UX

## Reflection
Building this project gave me hands-on experience with AWS serverless services like DynamoDB, Lambda, and API Gateway. I learned how to put together end-to-end CRUD operations, troubleshoot CORS issues between the backend and frontend, and set up IAM roles with least-privilege. The result was a fully deployed web app that connects smoothly to AWS on the backend.
