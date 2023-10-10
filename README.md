<h1>Server Documentation</h1>
<h2>Overview</h2>
This Express.js server serves as an API for working with the DALL-E model and handling posts with associated images. It integrates with Cloudinary for image storage and retrieval and uses the OpenAI API to generate images based on prompts.

Prerequisites
Before running the server, make sure you have the following dependencies installed:

<ul>
<li><strong>Node.js (v14 or later)</strong></li>
<li>NPM (Node Package Manager)</li>
<li>MongoDB (with the connection URL provided in the environment variable MONGODB_URL)</li>
<li>Cloudinary Account (with API credentials stored in environment variables ClOULDINARY_CLOUD_NAME, ClOULDINARY_API_KEY, and ClOULDINARY_API_SECRET)</li>
<li>OpenAI API Key (stored in the environment variable OPENAI_API_KEY)</li>
</ul>
<h1>Configuration</h1>
Ensure that you have set up your environment variables in a .env file in the root directory. Sample .env file:

`MONGODB_URL=your-mongodb-connection-url
ClOULDINARY_CLOUD_NAME=your-cloudinary-cloud-name
ClOULDINARY_API_KEY=your-cloudinary-api-key
ClOULDINARY_API_SECRET=your-cloudinary-api-secret
OPENAI_API_KEY=your-openai-api-key`

<h1>Starting the Server</h1>

run :

`npm start`

<strong>Your server will be available at http://localhost:8080</strong>

<h1>API Endpoints</h1>
<ul>
 <li> 1. /api/v1/post (Post Routes)</li>
  <li>GET /api/v1/post</li>
</ul>
Description: Get a list of posts stored in the MongoDB database.

Request Type: GET

<ul>
  <li><strong>Response:</strong></li> 
  <ul>
   <li> Status Code: 200 OK</li>
   <li> Content-Type: application/json</li>
  </ul>
</ul>
<ul>
  <strong>Error Responses:</strong>

<li>Status Code: 500 Internal Server Error</li>
<li>Content-Type: application/json</li>
</ul>

<h3>POST /api/v1/post</h3>
<strong><h4>Description: Create a new post and store it in the MongoDB database.</h4></strong>

Request Type: POST

Request Body:

Content-Type: application/json

`{
  "name": "Post Name",
  "prompt": "DALL-E Prompt",
  "photo": "Base64-encoded image data"
}
`
<strong><h3>Response</h3></strong>
<ul>
  <li>Status Code: 201 Created</li>
  <li>Content-Type: application/json</li>
</ul>

`{
  "success": true,
  "data": {
    "name": "Post Name",
    "prompt": "DALL-E Prompt",
    "photo": "URL to the uploaded image"
  }
}`




<h3> <span style="color:red" > WARING: </span> Since OpenAI going wild  you might have some issue while generating new image </h3>
Visit : https://al-photo-generating-app.vercel.app

![exam2](https://user-images.githubusercontent.com/43577099/219849210-3064182e-9ee0-4f1e-bf61-652feddc4a66.png)

![exm1](https://user-images.githubusercontent.com/43577099/219849224-59dda82d-8ff5-4320-bada-a6c9ab78500b.png)
