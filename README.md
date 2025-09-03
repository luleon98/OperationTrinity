# Grocery Checklist Project

## Overview
* The checklist will allow me to add, track, update, and delete a list of the groceries I need. I am building this for the sole reason to keep track of my grocery needs without having to go into my Notes app as I am tired of the basic Apple layout of its Notes. I will build this Checklist on AWS using different services, including: DynamoDB, API Gateway, Lambda, S3, Cloudfront, and Cognito. Maybe more.

## Screenshots / Demo
*(Insert screenshots, demo links, or architecture diagrams here)*  

## Architecture
Add a simple description or diagram of how it works:  
- Which AWS services or tools are used?  
- How do they interact?

*(Insert diagram here if possible)*  

## Tech Stack
- AWS Services: DynamoDB, Lambda, IAM, API Gateway ... 
- Languages: Python, JavaScript, etc.  
- Tools/Frameworks: Terraform, Docker, React, etc.  

## Deployment / Setup
There are two phases for this project. Phase 1 is the backend foundation and phase 2 is frontend launch.

1. Create a DynamoDB table and define a schema with a partition key and sort key. I set mine as userId and itemId, respectively. Both types will be strings.
2. Explore table items and create an item with desired attributes. In this case, I used name (string), quantity (number) and checked (boolean).
3. Create Lambda functions that will create items (POST), get items (GET), update items (PUT), and delete items (DELETE).
4. Create IAM roles to allow Lambda functions to create, get, update and delete items in DynamoDB. Ensure IAM roles have least privileges. Attach roles to respective Lambda functions.
5. After deploying code in Lambda, test functions with events to ensure dynamo db table is updated with new data that was added or removed via test events.
6. Integrate Lambda functions to API Gateway, using HTTP API, to frontend so we can call endpoints over HTTP. Add one route per Lambda function and deploy API.
7. Test Endpoints via Postman using the our API's invoke URL. After this point our full CRUD flow via API Gateway should be operational and ready for the frontend.
8. Next step: set up an index.html, upload it to S3 and host a static website there and go through cloud front or amplify (like first project!) ...

## Features & Learning
- Setting up a DynamoDB, creating a table schema, scanning and querying items in DynamoDB console, Index creation.
- Feature 2 / Concept learned  
- Feature 3 / Concept learned  

## Future Improvements
- [ ] Enhancement idea 1  
- [ ] Enhancement idea 2  
- [ ] Enhancement idea 3  

## Reflection
Short note on what you learned or practiced while building this project.
