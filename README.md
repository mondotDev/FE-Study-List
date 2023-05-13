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

Feel free to use this study packet as a reference to learn and review the mentioned topics. Good luck with your preparations for the front-end technical interview!