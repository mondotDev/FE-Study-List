## Step-by-Step Guide: Building a Contact Form with HTML, Bootstrap, and JavaScript (including server-side handling with Node.js)

### Step 1: Set up the HTML Structure

1. Create a new HTML file, such as `contact.html`, and open it in your preferred text editor.
2. Add the basic HTML structure by including the `<!DOCTYPE html>` declaration and the opening and closing `<html>`, `<head>`, and `<body>` tags.
3. Inside the `<body>` tag, create a `<form>` element to hold the contact form. You can add the `action` attribute to the `<form>` tag and set it to `""`, which means the form will submit to the current page URL.
4. Add input fields for the user to enter their name, email, and message. Use the `<input>` tag for single-line text inputs and the `<textarea>` tag for multi-line inputs. Be sure to include the `name` attribute for each input field to capture the form data.
5. Include a submit button using the `<button>` element with the `type="submit"` attribute.

```html
<!DOCTYPE html>
<html>
<head>
  <!-- Include Bootstrap CSS -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
</head>
<body>
  <form id="contact-form" action="" method="POST">
    <div class="form-group">
      <label for="name">Name</label>
      <input type="text" name="name" id="name" class="form-control" required>
    </div>
    <div class="form-group">
      <label for="email">Email</label>
      <input type="email" name="email" id="email" class="form-control" required>
    </div>
    <div class="form-group">
      <label for="message">Message</label>
      <textarea name="message" id="message" class="form-control" rows="5" required></textarea>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
  </form>

  <!-- Include JavaScript file -->
  <script src="contact.js"></script>
</body>
</html>
```

### Step 2: Style the Form with Bootstrap

1. To style the contact form using Bootstrap, you need to include the Bootstrap CSS library in your HTML file. You can do this by adding the following `<link>` tag within the `<head>` section:

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
```

2. Use Bootstrap's classes to style the form elements. For example, the `form-group` class can be added to group related form elements, and the `form-control` class can be applied to input fields to style them accordingly.

### Step 3: Validate the Form with JavaScript

1. Create a JavaScript file, such as `contact.js`, and save it in the same directory as your HTML file.
2. Open the `contact.js` file and begin by wrapping your code in a DOMContentLoaded event listener to ensure that the JavaScript runs after the HTML has finished loading.

```javascript
document.addEventListener('DOMContentLoaded', function() {
  // JavaScript code goes here
});
```

3. Inside the event listener, select the form using the `querySelector` method and add an event listener for the form's submit event. In the event listener, prevent the default form submission behavior using the `preventDefault` method to stop the form from being submitted and the page from reloading.

```javascript
document.addEventListener('DOMContentLoaded', function() {
  const form = document.querySelector('#contact-form');

  form.addEventListener('submit', function(event) {
    event.preventDefault();
    // Validation and form handling code goes here
  });
});
```

4. Perform form validation within the submit event listener to ensure that the required fields are filled out and that the email field follows a valid format. You can use regular expressions or a library like [Validator.js](https://github.com/validatorjs/validator.js) to perform email validation. If any validation errors occur, display appropriate error messages to the user.

```javascript
document.addEventListener('DOMContentLoaded', function() {
  const form = document.querySelector('#contact-form');

  form.addEventListener('submit', function(event) {
    event.preventDefault();

    // Validation code
    const name = document.querySelector('#name').value;
    const email = document.querySelector('#email').value;
    const message = document.querySelector('#message').value;

    if (name.trim() === '') {
      alert('Please enter your name');
      return;
    }

    if (email.trim() === '') {
      alert('Please enter your email');
      return;
    }

    if (!validator.isEmail(email)) {
      alert('Please enter a valid email address');
      return;
    }

    if (message.trim() === '') {
      alert('Please enter your message');
      return;
    }

    // Form submission code
    const formData = {
      name: name,
      email: email,
      message: message
    };

    // Make an AJAX request to the server
    const xhr = new XMLHttpRequest();
    xhr.open('POST', '/submit', true);
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.onreadystatechange = function() {
      if (xhr.readyState === XMLHttpRequest.DONE && xhr.status === 200) {
        alert('Form submitted successfully!');
        // Optionally, perform additional actions after form submission
      }
    };
    xhr.send(JSON.stringify(formData));
  });
});
```

5. Set up a server using Node.js to handle the form submission. You can use a framework like [Express.js](https://expressjs.com/) to simplify the server setup and route handling.

6. In your server-side JavaScript file (e.g., `server.js`), import the necessary modules and set up an Express server.

```javascript
const express = require('express');
const app = express();
const bodyParser = require('body-parser');

app.use(bodyParser.json());

// Handle form submission
app.post('/submit', function(req, res) {
  // Access form data
  const name = req.body.name;
  const email = req.body.email;
  const message = req.body.message;

  // Process the form data (e.g., send an email, store in a database, etc.)
  // ...

  // Send a response back to the client
  res.status(200).json({ message: 'Form submitted successfully!' });
});

// Start the server
const port = 3000; // Change this to the desired port number
app.listen(port, function() {
  console.log(`Server started on port ${port}`);
});
```

Make sure to install the required Node.js modules (`express` and `body-parser`) using npm.

That's it! You have now created a functional contact form with HTML, Bootstrap, and JavaScript, including server-side handling with Node.js. Remember to test your form thoroughly and ensure it functions as expected.