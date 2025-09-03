# Grocery Checklist Project

## Overview
* The Grocery Checklist is a web-based app to add, track, update, and delete grocery items. I built this to organize my grocery needs without relying on the default Notes app on my iPhone. This project is fully hosted on AWS and leverages multiple services including DynamoDB, Lambda, API Gateway, Amplify, and IAM. The architecture demonstrates serverless CRUD operations in a production-like environment.

## Screenshots / Demo
*(Insert screenshots, demo links, or architecture diagrams here)*  

## Architecture
The app follows a serverless architecture:
* DynamoDB → stores grocery items (userId as partition key, itemId as sort key)
* Lambda functions → implement Create, Read, Update, Delete operations
* API Gateway → exposes Lambda functions via RESTful HTTP endpoints
* Amplify → hosts the frontend (HTML/JS) and connects to API Gateway
* IAM roles → provide least privilege access for each Lambda function

(Add a simple architecture diagram showing the flow: Amplify → API Gateway → Lambda → DynamoDB) <-- similar to what is on the static website README

## Tech Stack
* AWS Services: DynamoDB, Lambda, IAM, API Gateway, Amplify
* Languages: JavaScript (Node.js)
* Tools/Frameworks: AWS Console, Postman

## Deployment / Setup
Phase 1 focuses on backend foundation and API integration:
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
- [ ] Enhancement idea 1  
- [ ] Enhancement idea 2  
- [ ] Enhancement idea 3  

## Reflection
Short note on what was learned or practiced while building this project.
