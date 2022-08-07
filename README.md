# RanchBeef

## Vendor Portal

This repository represents the frontend (customer facing) portal for vendors to order meat products, track those order and do statistical analysis on what their customer like the most.

### Stack

- NodeJS
- GraphQL
- AWS Lambda, RDS, SQS, Serverless
- Twilio

### Pages

- Signin
- Inventory ordering and settings
- Order Analysis/Product Feedback

### Stories

#### User Authentication

As an end user, I want to be able to have a secure login to my ranchbeef portal.  I want to have 2d authentication if I choose.

- Build a signin page that uses the ranchbeef theme with username and password fields.
- Do a POST to a Twilio API end point to authenticate user
- Use https to connect to Twilio API endpoint
- Build logic to consume Twilio response and produce proper page load or error message
- Add a logout button to each page that deauthenticates the end user and refreshes with the login page.

##### Inventory ordering and settings

As an end user, I want to be able to see available products to order, order history, currently automatic orders and their frequency and an option button to change auto order settings.

- Build a page that uses the ranchbeef theme and that has a tab that dynamically lists all products that are currently set to auto reorder.
- Make it so that each product shows details such as reorder date, amount of next order, and current rating by end user.
- Have a tab on this page that shows all available products that can be ordered.
- Create a Lambda RESTful endpoint using PUT to add or update product information
- Create a Lambda RESTful endpoint using GET to retrieve product information
- Create an RDS MySQL database that holds all order and product information
- Use AWS SQS for Asychronous API calls

##### Order analysis and product feedback

As an end user, I want to be able to see and compare order frequencies of each product we sell to our customers. I also want to be able to send feed back on each product based on our customer's comments.

- build page that uses the ranchbeef theme to display order history and frequency of each product.
- Make it so each product can accept a rating and textual feedback from the end user.
- Include a submit button for each product after a rating and feedback information has been entered.
- Create a Lambda RESTful endpoint using PUT to add or update product rating and feedback information
- Create a Lambda RESTful endpoint using GET to retrieve product rating and feedback information
- Create an RDS MySQL database that holds all order and product rating and feedback information
- Use AWS SQS for Asychronous API calls
