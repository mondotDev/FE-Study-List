# Front-End Technical Interview Study Packet

## HTML

- **Purpose of HTML:** HTML (Hypertext Markup Language) is used for creating the structure and content of web pages.
  
## CSS

- **Box Model:** The box model in CSS describes how elements are rendered on a web page. It consists of content, padding, border, and margin.
  
- **Selecting Elements:** To select an element with a specific ID in CSS, use the `#` symbol followed by the ID name (e.g., `#myElement`).

- **Inline vs. Block Elements:** 
    - Inline elements: They do not start on a new line and only take up the necessary width to contain their content.
    - Block elements: They start on a new line and occupy the full available width. They can have margins, padding, and width properties set.
  
## Responsive Web Design

- **Concept:** Responsive web design is an approach that aims to make web pages render well on various devices and window or screen sizes. It involves using flexible layouts, fluid images, and media queries to adapt the design.

## JavaScript

- **Purpose:** JavaScript is a programming language used for making web pages interactive and dynamic. It allows you to manipulate web page content, handle events, and communicate with servers.

- **Adding an Event Listener:** To add an event listener to a button element in JavaScript, you can use the `addEventListener` method. Example:

  ```javascript
  const button = document.querySelector('button');
  button.addEventListener('click', function() {
    // Code to be executed when the button is clicked
  });
  ```

- **== vs. === Operator:**
    - `==` (loose equality operator): It compares the values of two operands after converting their types if necessary. It performs type coercion.
    - `===` (strict equality operator): It compares the values and types of two operands. No type coercion is performed.

- **AJAX Request:** To make an AJAX (Asynchronous JavaScript and XML) request in JavaScript, you can use the `XMLHttpRequest` object or the more modern `fetch` API.

  ```javascript
  // Using XMLHttpRequest
  const xhr = new XMLHttpRequest();
  xhr.open('GET', 'https://api.example.com/data', true);
  xhr.onload = function() {
    // Code to handle the response
  };
  xhr.send();
  
  // Using fetch API
  fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => {
      // Code to handle the data
    })
    .catch(error => {
      // Code to handle errors
    });
  ```

## Version Control

- **Concept:** Version control is a system that records changes to files over time, allowing you to track and manage different versions of your code or project. It helps with collaboration, maintaining a history of changes, and reverting to previous versions if needed.

- **Popular Version Control System:** One popular version control system is Git, which is widely used for source code management. It offers features like branching, merging, and distributed collaboration.

## Study Guide: Building a Contact Form with HTML, Bootstrap, and JavaScript

### Step 1: Set up the HTML Structure

- Create a new HTML file and open it in a text editor.
- Add the basic HTML structure: `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>` tags.
- Inside the `<body>` tag, create a `<form>` element to hold the contact form.
- Add input fields for name, email, and message using `<input>` and `<textarea>` tags.
- Include a submit button using the `<button>` element.

### Step 2: Style the Form with Bootstrap

- Include the Bootstrap CSS library by adding the appropriate `<link>` tag within the `<head>` section of your HTML file.
- Use Bootstrap's classes to style the form elements, such as `form-group` and `form-control`.

### Step 3: Validate the Form with JavaScript

- Create a JavaScript file and wrap the code in a DOMContentLoaded event listener.
- Select the form using the `querySelector` method and add an event listener for the submit event.
- Prevent the default form submission behavior using `preventDefault`.
- Perform form validation to ensure the required fields are filled and the email field follows a valid format.
- Display appropriate error messages if validation fails.
- Optionally, use a library like Validator.js for email validation.
- Handle form submission by capturing the form data and making an AJAX request to the server.
- Create an XMLHttpRequest object, set its properties, and send the form data to the server.

### Step 4: Submit the Form Data (Server-side Handling with Node.js)

- Set up a server using Node.js, preferably with a framework like Express.js.
- Import necessary modules and set up an Express server.
- Use body-parser middleware to parse JSON data from the client.
- Create a route on the server to handle the form submission, typically using the HTTP POST method.
- Access the form data from the request object on the server.
- Process the form data according to your requirements (e.g., send an email, store in a database, etc.).
- Send a response back to the client to indicate successful form submission.