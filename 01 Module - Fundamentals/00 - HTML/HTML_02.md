# HTML Tutorial: Part 2

## 3. Forms and Tables

### HTML Forms

Forms allow users to interact with a website by submitting data. They're essential for everything from simple contact forms to complex applications.

#### Basic Form Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic HTML Form</title>
</head>
<body>
    <h1>Contact Form</h1>
    
    <form action="/submit-form" method="post">
        <!-- Text input -->
        <div>
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" placeholder="Enter your name" required>
        </div>
        
        <!-- Email input -->
        <div>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" placeholder="Enter your email" required>
        </div>
        
        <!-- Textarea for longer text -->
        <div>
            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="5" cols="30" placeholder="Type your message here"></textarea>
        </div>
        
        <!-- Submit button -->
        <div>
            <button type="submit">Send Message</button>
        </div>
    </form>
</body>
</html>

```

Let's examine the key components of this form:

- **`<form>` Element**: The container for all form controls. Important attributes include:
  - `action`: Specifies where to send the form data when submitted (typically a URL)
  - `method`: Specifies the HTTP method to use when submitting (`get` or `post`)
  
- **`<label>` Element**: Provides a text label for form controls. The `for` attribute links the label to a specific form control using its `id`.

- **`<input>` Element**: Creates various form controls based on its `type` attribute.
  - `type="text"`: Creates a basic single-line text input
  - `type="email"`: Creates a field that validates email format
  - `name`: Specifies the name of the input, which is sent with the form data
  - `placeholder`: Provides hint text that disappears when the user starts typing
  - `required`: Makes the field mandatory

- **`<textarea>` Element**: Creates a multi-line text input.
  - `rows` and `cols`: Define the visible dimensions

- **`<button>` Element**: Creates a clickable button.
  - `type="submit"`: Makes it submit the form when clicked

### Form Input Types

HTML5 introduced many specialized input types that provide built-in validation and appropriate mobile keyboards:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML5 Input Types</title>
</head>
<body>
    <h1>HTML5 Input Types</h1>
    
    <form action="/submit" method="post">
        <h2>Text Inputs</h2>
        
        <div>
            <label for="text">Text:</label>
            <input type="text" id="text" name="text" placeholder="Regular text input">
        </div>
        
        <div>
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" placeholder="Password field (masked)">
        </div>
        
        <div>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" placeholder="name@example.com">
        </div>
        
        <div>
            <label for="url">URL:</label>
            <input type="url" id="url" name="url" placeholder="https://example.com">
        </div>
        
        <div>
            <label for="tel">Telephone:</label>
            <input type="tel" id="tel" name="tel" placeholder="(123) 456-7890">
        </div>
        
        <div>
            <label for="search">Search:</label>
            <input type="search" id="search" name="search" placeholder="Search...">
        </div>
        
        <h2>Numeric Inputs</h2>
        
        <div>
            <label for="number">Number:</label>
            <input type="number" id="number" name="number" min="0" max="100" step="1" value="50">
        </div>
        
        <div>
            <label for="range">Range (Slider):</label>
            <input type="range" id="range" name="range" min="0" max="100" step="5" value="50">
            <span id="rangeValue">50</span>
        </div>
        
        <h2>Date and Time Inputs</h2>
        
        <div>
            <label for="date">Date:</label>
            <input type="date" id="date" name="date">
        </div>
        
        <div>
            <label for="time">Time:</label>
            <input type="time" id="time" name="time">
        </div>
        
        <div>
            <label for="datetime-local">Date and Time:</label>
            <input type="datetime-local" id="datetime-local" name="datetime-local">
        </div>
        
        <div>
            <label for="month">Month:</label>
            <input type="month" id="month" name="month">
        </div>
        
        <div>
            <label for="week">Week:</label>
            <input type="week" id="week" name="week">
        </div>
        
        <h2>Color Picker</h2>
        
        <div>
            <label for="color">Color:</label>
            <input type="color" id="color" name="color" value="#3366cc">
        </div>
        
        <h2>File Upload</h2>
        
        <div>
            <label for="file">Single File:</label>
            <input type="file" id="file" name="file">
        </div>
        
        <div>
            <label for="multiple-files">Multiple Files:</label>
            <input type="file" id="multiple-files" name="multiple-files" multiple>
        </div>
        
        <h2>Hidden Input</h2>
        
        <div>
            <input type="hidden" id="user-id" name="user-id" value="12345">
            <p><em>Note: Hidden inputs are not visible to users but are included when the form is submitted.</em></p>
        </div>
        
        <button type="submit">Submit Form</button>
    </form>
    
    <script>
        // Simple script to show the range value
        const rangeInput = document.getElementById('range');
        const rangeValue = document.getElementById('rangeValue');
        
        rangeInput.addEventListener('input', function() {
            rangeValue.textContent = this.value;
        });
    </script>
</body>
</html>

```

Key input types and their purposes:

1. **Text Inputs**:
   - `text`: Basic text input
   - `password`: Masked text input for sensitive information
   - `email`: For email addresses (validates format)
   - `url`: For web addresses (validates format)
   - `tel`: For telephone numbers
   - `search`: For search queries (often has an "×" to clear the input)

2. **Numeric Inputs**:
   - `number`: For numeric input with up/down buttons
   - `range`: Creates a slider control

3. **Date and Time Inputs**:
   - `date`: For selecting a date
   - `time`: For selecting a time
   - `datetime-local`: For selecting both date and time
   - `month`: For selecting a month and year
   - `week`: For selecting a week and year

4. **Other Specialized Inputs**:
   - `color`: Creates a color picker
   - `file`: For uploading files
   - `hidden`: Not visible to users but included in form submission

Important attributes for input fields:

- `min`, `max`, `step`: For number and range inputs
- `pattern`: For specifying a regular expression pattern for validation
- `required`: Makes the field mandatory
- `disabled`: Makes the field non-editable
- `readonly`: Makes the field non-editable but still included in form submission
- `multiple`: Allows multiple values (for file inputs)

### Checkboxes and Radio Buttons

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Checkboxes and Radio Buttons</title>
</head>
<body>
    <h1>Checkboxes and Radio Buttons</h1>
    
    <form action="/submit" method="post">
        <h2>Checkboxes (Multiple Selection)</h2>
        <p>Which fruits do you like? (Select all that apply)</p>
        
        <div>
            <input type="checkbox" id="apple" name="fruits" value="apple">
            <label for="apple">Apple</label>
        </div>
        
        <div>
            <input type="checkbox" id="banana" name="fruits" value="banana">
            <label for="banana">Banana</label>
        </div>
        
        <div>
            <input type="checkbox" id="orange" name="fruits" value="orange">
            <label for="orange">Orange</label>
        </div>
        
        <div>
            <input type="checkbox" id="strawberry" name="fruits" value="strawberry">
            <label for="strawberry">Strawberry</label>
        </div>
        
        <h2>Radio Buttons (Single Selection)</h2>
        <p>What is your favorite coding language? (Select one)</p>
        
        <div>
            <input type="radio" id="html" name="language" value="html" checked>
            <label for="html">HTML</label>
        </div>
        
        <div>
            <input type="radio" id="css" name="language" value="css">
            <label for="css">CSS</label>
        </div>
        
        <div>
            <input type="radio" id="javascript" name="language" value="javascript">
            <label for="javascript">JavaScript</label>
        </div>
        
        <div>
            <input type="radio" id="python" name="language" value="python">
            <label for="python">Python</label>
        </div>
        
        <button type="submit">Submit</button>
    </form>
</body>
</html>

```

**Checkboxes** allow users to select multiple options from a group:
- Created with `<input type="checkbox">`
- Use the same `name` attribute for related checkboxes
- Each checkbox has a different `value` attribute
- When submitted, all checked values for the same name are sent

**Radio buttons** allow users to select exactly one option from a group:
- Created with `<input type="radio">`
- All related radio buttons must have the same `name` attribute
- Each radio button has a different `value` attribute
- Only the selected radio button's value is sent when the form is submitted
- Add `checked` attribute to pre-select one option

### Select Dropdowns and Datalists

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Select Dropdowns and Datalists</title>
</head>
<body>
    <h1>Select Dropdowns and Datalists</h1>
    
    <form action="/submit" method="post">
        <h2>Basic Select Dropdown</h2>
        <div>
            <label for="country">Select a country:</label>
            <select id="country" name="country">
                <option value="">-- Please choose a country --</option>
                <option value="us">United States</option>
                <option value="ca">Canada</option>
                <option value="uk">United Kingdom</option>
                <option value="au">Australia</option>
                <option value="jp">Japan</option>
            </select>
        </div>
        
        <h2>Select with Option Groups</h2>
        <div>
            <label for="car">Select a car:</label>
            <select id="car" name="car">
                <option value="">-- Please choose a car --</option>
                <optgroup label="American">
                    <option value="ford">Ford</option>
                    <option value="chevrolet">Chevrolet</option>
                    <option value="dodge">Dodge</option>
                </optgroup>
                <optgroup label="European">
                    <option value="volkswagen">Volkswagen</option>
                    <option value="bmw">BMW</option>
                    <option value="mercedes">Mercedes</option>
                </optgroup>
                <optgroup label="Asian">
                    <option value="toyota">Toyota</option>
                    <option value="honda">Honda</option>
                    <option value="hyundai">Hyundai</option>
                </optgroup>
            </select>
        </div>
        
        <h2>Multiple Select</h2>
        <div>
            <label for="skills">Select your skills (hold Ctrl/Cmd to select multiple):</label>
            <select id="skills" name="skills" multiple size="5">
                <option value="html">HTML</option>
                <option value="css">CSS</option>
                <option value="javascript">JavaScript</option>
                <option value="php">PHP</option>
                <option value="python">Python</option>
                <option value="java">Java</option>
                <option value="sql">SQL</option>
            </select>
        </div>
        
        <h2>Datalist (Autocomplete)</h2>
        <div>
            <label for="browser">Choose your browser:</label>
            <input list="browsers" id="browser" name="browser">
            <datalist id="browsers">
                <option value="Chrome">
                <option value="Firefox">
                <option value="Safari">
                <option value="Edge">
                <option value="Opera">
            </datalist>
        </div>
        
        <button type="submit">Submit</button>
    </form>
</body>
</html>

```

**Select Dropdown** (`<select>`) creates a dropdown menu:
- Contains `<option>` elements for each choice
- `<optgroup>` can be used to group related options
- Add `multiple` attribute to allow multiple selections
- The `size` attribute determines how many options are visible at once

**Datalist** (`<datalist>`) provides autocomplete suggestions for text inputs:
- Links to an input using the `list` attribute
- Contains `<option>` elements with suggestions
- Users can still enter values not in the list
- Combines flexibility of text input with guidance of a dropdown

### Form Organization

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Organization</title>
</head>
<body>
    <h1>Registration Form</h1>
    
    <form action="/register" method="post">
        <!-- Fieldset for personal information -->
        <fieldset>
            <legend>Personal Information</legend>
            
            <div>
                <label for="first-name">First Name:</label>
                <input type="text" id="first-name" name="first-name" required>
            </div>
            
            <div>
                <label for="last-name">Last Name:</label>
                <input type="text" id="last-name" name="last-name" required>
            </div>
            
            <div>
                <label for="dob">Date of Birth:</label>
                <input type="date" id="dob" name="dob" required>
            </div>
            
            <div>
                <label for="gender">Gender:</label>
                <select id="gender" name="gender">
                    <option value="">-- Select --</option>
                    <option value="male">Male</option>
                    <option value="female">Female</option>
                    <option value="non-binary">Non-binary</option>
                    <option value="prefer-not-to-say">Prefer not to say</option>
                </select>
            </div>
        </fieldset>
        
        <!-- Fieldset for contact information -->
        <fieldset>
            <legend>Contact Information</legend>
            
            <div>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
            </div>
            
            <div>
                <label for="phone">Phone:</label>
                <input type="tel" id="phone" name="phone">
            </div>
            
            <div>
                <label for="address">Address:</label>
                <textarea id="address" name="address" rows="3"></textarea>
            </div>
        </fieldset>
        
        <!-- Fieldset for account information -->
        <fieldset>
            <legend>Account Information</legend>
            
            <div>
                <label for="username">Username:</label>
                <input type="text" id="username" name="username" required>
            </div>
            
            <div>
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required>
            </div>
            
            <div>
                <label for="confirm-password">Confirm Password:</label>
                <input type="password" id="confirm-password" name="confirm-password" required>
            </div>
        </fieldset>
        
        <!-- Terms and conditions -->
        <div>
            <input type="checkbox" id="terms" name="terms" required>
            <label for="terms">I agree to the <a href="/terms">Terms and Conditions</a></label>
        </div>
        
        <!-- Form buttons -->
        <div>
            <button type="submit">Register</button>
            <button type="reset">Clear Form</button>
        </div>
    </form>
</body>
</html>

```

**Fieldset and Legend** help organize forms into logical sections:
- `<fieldset>` groups related form controls together
- `<legend>` provides a caption for the fieldset

**Button Types**:
- `type="submit"`: Submits the form
- `type="reset"`: Resets all form controls to default values
- `type="button"`: Generic button (doesn't submit the form)

### HTML Tables

Tables are used to display data in rows and columns:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Table Structure</title>
</head>
<body>
    <h1>Basic HTML Table</h1>
    
    <table border="1">
        <!-- Table Caption -->
        <caption>Employee Information</caption>
        
        <!-- Table Header -->
        <thead>
            <tr>
                <th>ID</th>
                <th>Name</th>
                <th>Department</th>
                <th>Position</th>
                <th>Salary</th>
            </tr>
        </thead>
        
        <!-- Table Body -->
        <tbody>
            <tr>
                <td>1001</td>
                <td>John Smith</td>
                <td>Marketing</td>
                <td>Manager</td>
                <td>$85,000</td>
            </tr>
            <tr>
                <td>1002</td>
                <td>Jane Doe</td>
                <td>Engineering</td>
                <td>Senior Developer</td>
                <td>$95,000</td>
            </tr>
            <tr>
                <td>1003</td>
                <td>Bob Johnson</td>
                <td>Sales</td>
                <td>Representative</td>
                <td>$65,000</td>
            </tr>
            <tr>
                <td>1004</td>
                <td>Mary Williams</td>
                <td>Human Resources</td>
                <td>Director</td>
                <td>$78,000</td>
            </tr>
        </tbody>
        
        <!-- Table Footer -->
        <tfoot>
            <tr>
                <td colspan="4">Average Salary:</td>
                <td>$80,750</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>

```

**Basic Table Structure**:
- `<table>`: Container for the entire table
- `<caption>`: Provides a title or explanation for the table
- `<thead>`: Groups the header content
- `<tbody>`: Groups the main content
- `<tfoot>`: Groups the footer content
- `<tr>`: Defines a table row
- `<th>`: Defines a header cell
- `<td>`: Defines a data cell

### Advanced Table Features

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Advanced HTML Table Features</title>
</head>
<body>
    <h1>Advanced HTML Table Features</h1>
    
    <h2>Column and Row Spanning</h2>
    <table border="1">
        <caption>Product Inventory by Region</caption>
        <thead>
            <tr>
                <th rowspan="2">Product</th>
                <th colspan="3">Region</th>
            </tr>
            <tr>
                <th>North</th>
                <th>South</th>
                <th>East</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Widget A</td>
                <td>28</td>
                <td>35</td>
                <td>15</td>
            </tr>
            <tr>
                <td>Widget B</td>
                <td>12</td>
                <td>18</td>
                <td>22</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td>Total</td>
                <td>40</td>
                <td>53</td>
                <td>37</td>
            </tr>
        </tfoot>
    </table>
    
    <h2>Column Groups</h2>
    <table border="1">
        <caption>Quarterly Sales</caption>
        <colgroup>
            <col style="background-color: #f0f0f0;">
            <col span="4" style="background-color: #e0f0ff;">
        </colgroup>
        <thead>
            <tr>
                <th>Product</th>
                <th>Q1</th>
                <th>Q2</th>
                <th>Q3</th>
                <th>Q4</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Product A</td>
                <td>$10,000</td>
                <td>$12,000</td>
                <td>$15,000</td>
                <td>$18,000</td>
            </tr>
            <tr>
                <td>Product B</td>
                <td>$8,000</td>
                <td>$9,500</td>
                <td>$11,000</td>
                <td>$13,500</td>
            </tr>
        </tbody>
    </table>
    
    <h2>Accessible Table with Scope and Headers</h2>
    <table border="1">
        <caption>Employee Schedule</caption>
        <thead>
            <tr>
                <th scope="col">Name</th>
                <th scope="col">Monday</th>
                <th scope="col">Tuesday</th>
                <th scope="col">Wednesday</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th scope="row">Alice</th>
                <td>9 AM - 5 PM</td>
                <td>9 AM - 5 PM</td>
                <td>Off</td>
            </tr>
            <tr>
                <th scope="row">Bob</th>
                <td>Off</td>
                <td>9 AM - 5 PM</td>
                <td>9 AM - 5 PM</td>
            </tr>
            <tr>
                <th scope="row">Charlie</th>
                <td>9 AM - 5 PM</td>
                <td>Off</td>
                <td>9 AM - 5 PM</td>
            </tr>
        </tbody>
    </table>
</body>
</html>

```

**Column and Row Spanning**:
- `colspan="n"`: Makes a cell span multiple columns
- `rowspan="n"`: Makes a cell span multiple rows

**Column Groups**:
- `<colgroup>` and `<col>`: Used to specify properties for entire columns
- Useful for applying styles to columns without affecting individual cells

**Accessibility Attributes**:
- `scope="col"`: Indicates a header cell applies to the entire column
- `scope="row"`: Indicates a header cell applies to the entire row
- These attributes help screen readers interpret tables correctly

## 4. Advanced HTML Features

### iframes

The `<iframe>` element allows you to embed another HTML document within the current one:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML iframes</title>
</head>
<body>
    <h1>Working with iframes</h1>
    
    <h2>Basic iframe</h2>
    <iframe src="https://www.example.com" width="600" height="400" title="Example Website"></iframe>
    
    <h2>iframe with Fallback Content</h2>
    <iframe src="https://www.example.com" width="600" height="400" title="Example Website">
        <p>Your browser does not support iframes. Visit <a href="https://www.example.com">example.com</a> directly.</p>
    </iframe>
    
    <h2>iframe with Sandbox Attribute</h2>
    <iframe src="https://www.example.com" width="600" height="400" 
            sandbox="allow-same-origin allow-scripts"
            title="Sandboxed Example">
    </iframe>
    
    <h2>Embedding a YouTube Video</h2>
    <iframe width="560" height="315" 
            src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
            title="YouTube video player" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen>
    </iframe>
    
    <h2>Embedding a Google Map</h2>
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d6049.881319200985!2d-74.0059729!3d40.7127753!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c2588f046ee661%3A0xa0b3281fcecc08c!2sManhattan%2C%20New%20York%2C%20NY!5e0!3m2!1sen!2sus!4v1643819760119!5m2!1sen!2sus" 
            width="600" height="450" 
            style="border:0;" 
            allowfullscreen="" 
            loading="lazy"
            title="Google Map of Manhattan">
    </iframe>
</body>
</html>

```

**Key iframe attributes**:
- `src`: The URL of the page to embed
- `width` and `height`: Dimensions of the iframe
- `title`: Improves accessibility by describing the iframe content
- `sandbox`: Restricts capabilities of the embedded content for security
- `allow`: Specifies features the iframe is allowed to use (like camera, microphone)
- `allowfullscreen`: Allows the iframe content to go fullscreen
- `loading="lazy"`: Defers loading of off-screen iframes until they come into view

**Common uses for iframes**:
- Embedding content from third-party sites (videos, maps, etc.)
- Isolating widgets or interactive elements
- Creating sandboxed environments for user-generated content

**Security considerations**:
- Use the `sandbox` attribute to restrict capabilities
- Add the `referrerpolicy` attribute to control what information is sent to the embedded site
- Consider using the Content Security Policy (CSP) to restrict what can be embedded

### The Canvas Element

The `<canvas>` element provides a drawing surface for JavaScript:

Let me continue with the Canvas Element explanation and examples:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Canvas Element</title>
</head>
<body>
    <h1>HTML Canvas Examples</h1>
    
    <h2>Basic Shape Drawing</h2>
    <canvas id="shapes" width="400" height="200" style="border: 1px solid #000;"></canvas>
    
    <h2>Gradient and Text</h2>
    <canvas id="gradient" width="400" height="200" style="border: 1px solid #000;"></canvas>
    
    <h2>Simple Animation</h2>
    <canvas id="animation" width="400" height="200" style="border: 1px solid #000;"></canvas>
    
    <script>
        // Basic shapes
        const shapesCanvas = document.getElementById('shapes');
        const shapesCtx = shapesCanvas.getContext('2d');
        
        // Rectangle
        shapesCtx.fillStyle = 'blue';
        shapesCtx.fillRect(10, 10, 100, 80);
        
        // Circle
        shapesCtx.beginPath();
        shapesCtx.arc(200, 50, 40, 0, 2 * Math.PI);
        shapesCtx.fillStyle = 'red';
        shapesCtx.fill();
        
        // Line
        shapesCtx.beginPath();
        shapesCtx.moveTo(300, 20);
        shapesCtx.lineTo(350, 100);
        shapesCtx.strokeStyle = 'green';
        shapesCtx.lineWidth = 5;
        shapesCtx.stroke();
        
        // Triangle
        shapesCtx.beginPath();
        shapesCtx.moveTo(50, 150);
        shapesCtx.lineTo(100, 100);
        shapesCtx.lineTo(150, 150);
        shapesCtx.closePath();
        shapesCtx.fillStyle = 'purple';
        shapesCtx.fill();
        
        // Gradient and Text
        const gradientCanvas = document.getElementById('gradient');
        const gradientCtx = gradientCanvas.getContext('2d');
        
        // Create a linear gradient
        const gradient = gradientCtx.createLinearGradient(0, 0, 400, 0);
        gradient.addColorStop(0, 'blue');
        gradient.addColorStop(0.5, 'purple');
        gradient.addColorStop(1, 'red');
        
        // Fill a rectangle with the gradient
        gradientCtx.fillStyle = gradient;
        gradientCtx.fillRect(0, 0, 400, 100);
        
        // Add text
        gradientCtx.font = 'bold 30px Arial';
        gradientCtx.fillStyle = 'white';
        gradientCtx.textAlign = 'center';
        gradientCtx.fillText('Canvas Text Example', 200, 60);
        
        // Add a shadow to text
        gradientCtx.shadowColor = 'rgba(0, 0, 0, 0.5)';
        gradientCtx.shadowBlur = 5;
        gradientCtx.shadowOffsetX = 3;
        gradientCtx.shadowOffsetY = 3;
        gradientCtx.fillText('With Shadow Effect', 200, 150);
        
        // Simple Animation
        const animCanvas = document.getElementById('animation');
        const animCtx = animCanvas.getContext('2d');
        
        let x = 20;
        let y = 100;
        let radius = 20;
        let dx = 2;
        
        function animate() {
            // Clear the canvas
            animCtx.clearRect(0, 0, animCanvas.width, animCanvas.height);
            
            // Draw the circle
            animCtx.beginPath();
            animCtx.arc(x, y, radius, 0, Math.PI * 2);
            animCtx.fillStyle = 'orange';
            animCtx.fill();
            
            // Update position
            x += dx;
            
            // Reverse direction if hitting the edges
            if (x + radius > animCanvas.width || x - radius < 0) {
                dx = -dx;
            }
            
            // Request next animation frame
            requestAnimationFrame(animate);
        }
        
        // Start the animation
        animate();
    </script>
</body>
</html>

```

The `<canvas>` element creates a blank drawing surface that you can use with JavaScript to draw graphics, animations, games, visualizations, and other visual elements. Unlike SVG (which we'll cover later), Canvas is pixel-based and manipulated entirely through JavaScript.

### Key Concepts for Canvas:

1. **The Canvas Context**: 
   Before you can draw on a canvas, you need to get its context using `getContext()`. The most commonly used context is "2d" for two-dimensional drawing.

2. **Basic Drawing Operations**:
   - **Rectangles**: `fillRect()`, `strokeRect()`, `clearRect()`
   - **Paths**: Create custom shapes using `beginPath()`, `moveTo()`, `lineTo()`, `arc()`, `closePath()`
   - **Colors and Styles**: Control appearance with `fillStyle`, `strokeStyle`, `lineWidth`
   - **Text**: Draw text with `fillText()` and `strokeText()`
   - **Gradients**: Create linear or radial gradients with `createLinearGradient()` or `createRadialGradient()`
   - **Images**: Draw images with `drawImage()`

3. **Animation and Interaction**:
   - Use `requestAnimationFrame()` for smooth animations
   - Clear the canvas with `clearRect()` before each animation frame
   - Respond to user interactions like mouse movements or touch events

### Advantages of Canvas:

- **Performance**: Excellent for animations or applications with many objects
- **Pixel manipulation**: Direct access to pixel data
- **Game development**: Ideal for 2D games
- **Complex visualizations**: Good for charts, data visualizations, and interactive graphics

### Limitations of Canvas:

- **Accessibility**: Canvas content isn't inherently accessible to screen readers
- **Scalability**: Canvas elements don't scale naturally like vector graphics (SVG)
- **No DOM interaction**: Canvas elements are just pixels, not DOM objects that can be selected or manipulated

### SVG Graphics

SVG (Scalable Vector Graphics) is an XML-based format for vector graphics that can be directly embedded in HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SVG in HTML</title>
    <style>
        /* Styling SVG elements with CSS */
        .svg-circle:hover {
            fill: red;
        }
        
        #animated-rect {
            animation: pulse 2s infinite alternate;
        }
        
        @keyframes pulse {
            from { fill: blue; }
            to { fill: purple; }
        }
    </style>
</head>
<body>
    <h1>Working with SVG in HTML</h1>
    
    <h2>Basic SVG Shapes</h2>
    <svg width="400" height="200" viewBox="0 0 400 200">
        <!-- Rectangle -->
        <rect x="10" y="10" width="100" height="80" fill="blue" />
        
        <!-- Circle -->
        <circle cx="200" cy="50" r="40" fill="red" class="svg-circle" />
        
        <!-- Line -->
        <line x1="300" y1="20" x2="350" y2="100" stroke="green" stroke-width="5" />
        
        <!-- Polygon (Triangle) -->
        <polygon points="50,150 100,100 150,150" fill="purple" />
        
        <!-- Text -->
        <text x="200" y="150" font-family="Arial" font-size="24" text-anchor="middle">SVG Text</text>
    </svg>
    
    <h2>Path Element</h2>
    <svg width="400" height="150" viewBox="0 0 400 150">
        <!-- Path: M=moveto, L=lineto, Q=quadratic curve, Z=closepath -->
        <path d="M 10,75 L 50,15 Q 100,100 150,25 L 200,75 L 250,25 Q 300,100 350,15 L 390,75" 
              fill="none" stroke="blue" stroke-width="3" />
    </svg>
    
    <h2>Gradient and Animation</h2>
    <svg width="400" height="200" viewBox="0 0 400 200">
        <!-- Linear gradient definition -->
        <defs>
            <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" stop-color="blue" />
                <stop offset="50%" stop-color="purple" />
                <stop offset="100%" stop-color="red" />
            </linearGradient>
        </defs>
        
        <!-- Rectangle with gradient fill -->
        <rect x="10" y="10" width="380" height="80" fill="url(#gradient)" />
        
        <!-- Animated rectangle -->
        <rect id="animated-rect" x="100" y="120" width="200" height="50" rx="10" ry="10" />
    </svg>
    
    <h2>SVG with Interactivity</h2>
    <svg width="400" height="100" viewBox="0 0 400 100">
        <rect id="interactive-rect" x="50" y="20" width="300" height="60" rx="10" ry="10" 
              fill="lightblue" stroke="blue" />
        <text x="200" y="55" text-anchor="middle" font-family="Arial" font-size="16">Click me!</text>
    </svg>
    
    <script>
        // Adding interactivity with JavaScript
        const interactiveRect = document.getElementById('interactive-rect');
        interactiveRect.addEventListener('click', function() {
            const currentFill = this.getAttribute('fill');
            this.setAttribute('fill', currentFill === 'lightblue' ? 'lightgreen' : 'lightblue');
        });
    </script>
</body>
</html>

```

SVG (Scalable Vector Graphics) is an XML-based markup language for describing two-dimensional vector graphics. Unlike Canvas, which draws pixels, SVG creates shapes as objects in the DOM.

### Key SVG Elements:

1. **Basic Shapes**:
   - `<rect>`: Rectangles
   - `<circle>` and `<ellipse>`: Circular shapes
   - `<line>`: Straight lines
   - `<polyline>`: Connected line segments
   - `<polygon>`: Closed shapes with straight sides
   - `<text>`: Text elements

2. **Advanced Elements**:
   - `<path>`: Complex shapes using a compact command syntax
   - `<g>`: Groups related elements together
   - `<defs>` and `<use>`: Define elements for reuse
   - `<mask>`, `<clipPath>`: Control visibility of elements
   - `<linearGradient>`, `<radialGradient>`: Create color gradients
   - `<filter>`: Apply visual effects

### Advantages of SVG:

- **Scalability**: SVG images remain crisp at any resolution
- **Accessibility**: Text elements remain accessible to screen readers
- **DOM Integration**: SVG elements are part of the DOM and can be selected, modified, and styled
- **CSS Support**: SVG elements can be styled with CSS
- **Animation**: Supports both CSS animations and SMIL animations
- **Lower file size**: Often smaller than raster images for simple graphics

### Canvas vs. SVG: When to Use Each

**Use Canvas when**:
- You need to render many objects (hundreds or thousands)
- You're building games or complex animations
- You need pixel-level manipulation
- Performance is critical

**Use SVG when**:
- You need scalable graphics that look sharp at any size
- Accessibility is important
- You want to manipulate elements with JavaScript after drawing
- You want to style elements with CSS
- You're working with fewer, larger objects

### Data Attributes

HTML5 introduced data attributes, which allow you to store custom data in HTML elements:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Data Attributes</title>
    <style>
        .product {
            border: 1px solid #ddd;
            padding: 15px;
            margin: 10px;
            display: inline-block;
            width: 200px;
        }
        
        .highlight {
            background-color: #fffacd;
        }
    </style>
</head>
<body>
    <h1>Using Data Attributes</h1>
    
    <div id="product-list">
        <div class="product" 
             data-id="1001" 
             data-name="Coffee Maker" 
             data-price="49.99" 
             data-category="kitchen" 
             data-in-stock="true">
            <h3>Coffee Maker</h3>
            <p>Price: $49.99</p>
            <button class="details-btn">Show Details</button>
        </div>
        
        <div class="product" 
             data-id="1002" 
             data-name="Blender" 
             data-price="39.99" 
             data-category="kitchen" 
             data-in-stock="true">
            <h3>Blender</h3>
            <p>Price: $39.99</p>
            <button class="details-btn">Show Details</button>
        </div>
        
        <div class="product" 
             data-id="1003" 
             data-name="Wireless Headphones" 
             data-price="89.99" 
             data-category="electronics" 
             data-in-stock="false">
            <h3>Wireless Headphones</h3>
            <p>Price: $89.99</p>
            <button class="details-btn">Show Details</button>
        </div>
    </div>
    
    <div id="details-output" style="margin-top: 20px; padding: 10px; border: 1px solid #ddd;">
        <h2>Product Details</h2>
        <p>Click a product's button to see full details</p>
    </div>
    
    <h2>Filtering</h2>
    <button id="show-kitchen">Show Kitchen Products</button>
    <button id="show-electronics">Show Electronics Products</button>
    <button id="show-all">Show All Products</button>
    <button id="show-in-stock">Show Only In-Stock Items</button>
    
    <script>
        // Accessing data attributes
        const detailsButtons = document.querySelectorAll('.details-btn');
        const detailsOutput = document.getElementById('details-output');
        
        detailsButtons.forEach(button => {
            button.addEventListener('click', function() {
                const product = this.parentElement;
                const id = product.dataset.id;
                const name = product.dataset.name;
                const price = product.dataset.price;
                const category = product.dataset.category;
                const inStock = product.dataset.inStock === 'true' ? 'Yes' : 'No';
                
                detailsOutput.innerHTML = `
                    <h2>Product Details</h2>
                    <p><strong>ID:</strong> ${id}</p>
                    <p><strong>Name:</strong> ${name}</p>
                    <p><strong>Price:</strong> $${price}</p>
                    <p><strong>Category:</strong> ${category}</p>
                    <p><strong>In Stock:</strong> ${inStock}</p>
                `;
            });
        });
        
        // Filtering based on data attributes
        document.getElementById('show-kitchen').addEventListener('click', function() {
            filterProducts('category', 'kitchen');
        });
        
        document.getElementById('show-electronics').addEventListener('click', function() {
            filterProducts('category', 'electronics');
        });
        
        document.getElementById('show-all').addEventListener('click', function() {
            const products = document.querySelectorAll('.product');
            products.forEach(product => {
                product.style.display = 'inline-block';
            });
        });
        
        document.getElementById('show-in-stock').addEventListener('click', function() {
            filterProducts('in-stock', 'true');
        });
        
        function filterProducts(attribute, value) {
            const products = document.querySelectorAll('.product');
            products.forEach(product => {
                if (product.dataset[attribute] === value) {
                    product.style.display = 'inline-block';
                } else {
                    product.style.display = 'none';
                }
            });
        }
    </script>
</body>
</html>

```

Data attributes provide a way to store extra information on standard HTML elements without using non-standard attributes or extra DOM properties.

### Key Features of Data Attributes:

1. **Naming Convention**:
   - Always start with `data-`
   - Follow with a lowercase name (can contain hyphens)
   - Examples: `data-id`, `data-user-name`, `data-animation-duration`

2. **Accessing Data Attributes**:
   - In JavaScript: use the `dataset` property
     - Example: `element.dataset.id` accesses `data-id`
     - Hyphenated attributes become camelCase: `data-user-name` becomes `dataset.userName`
   - In CSS: use attribute selectors
     - Example: `[data-category="electronics"] { color: blue; }`
     - Or with the `attr()` function: `content: attr(data-price);`

3. **Common Uses**:
   - Storing configuration data for JavaScript components
   - Marking elements for selection or processing
   - Associating data with the elements displaying it
   - Creating hooks for JavaScript behavior
   - Storing state information
   - Configuring animations or transitions

### Microdata and SEO

HTML microdata helps search engines better understand your content by providing structured data:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Microdata Example</title>
</head>
<body>
    <h1>HTML Microdata for SEO</h1>
    
    <h2>Product Example</h2>
    <div itemscope itemtype="https://schema.org/Product">
        <h3 itemprop="name">Wireless Noise-Cancelling Headphones</h3>
        <img itemprop="image" src="headphones.jpg" alt="Wireless Headphones">
        
        <div itemprop="description">
            Premium wireless headphones with active noise cancellation, 
            30-hour battery life, and comfortable over-ear design.
        </div>
        
        <div itemprop="offers" itemscope itemtype="https://schema.org/Offer">
            <span itemprop="price">$199.99</span>
            <meta itemprop="priceCurrency" content="USD">
            <link itemprop="availability" href="https://schema.org/InStock">In Stock
        </div>
        
        <div itemprop="aggregateRating" itemscope itemtype="https://schema.org/AggregateRating">
            <meta itemprop="ratingValue" content="4.5">
            <meta itemprop="reviewCount" content="89">
            <span>★★★★½ (89 reviews)</span>
        </div>
        
        <div itemprop="brand" itemscope itemtype="https://schema.org/Brand">
            <meta itemprop="name" content="AudioTech">
        </div>
    </div>
    
    <h2>Recipe Example</h2>
    <div itemscope itemtype="https://schema.org/Recipe">
        <h3 itemprop="name">Classic Chocolate Chip Cookies</h3>
        <img itemprop="image" src="cookies.jpg" alt="Chocolate Chip Cookies">
        
        <div>
            <span itemprop="author" itemscope itemtype="https://schema.org/Person">
                <span itemprop="name">Jane Smith</span>
            </span>
        </div>
        
        <div>
            <meta itemprop="datePublished" content="2025-01-15">
            Published: January 15, 2025
        </div>
        
        <div>
            <span itemprop="description">
                The perfect chocolate chip cookies - crispy on the outside, chewy on the inside!
            </span>
        </div>
        
        <div>
            <span>Prep Time: <meta itemprop="prepTime" content="PT20M">20 minutes</span><br>
            <span>Cook Time: <meta itemprop="cookTime" content="PT10M">10 minutes</span><br>
            <span>Total Time: <meta itemprop="totalTime" content="PT30M">30 minutes</span><br>
            <span>Yield: <span itemprop="recipeYield">24 cookies</span></span>
        </div>
        
        <div>
            <h4>Ingredients:</h4>
            <ul>
                <li itemprop="recipeIngredient">2 1/4 cups all-purpose flour</li>
                <li itemprop="recipeIngredient">1 teaspoon baking soda</li>
                <li itemprop="recipeIngredient">1 teaspoon salt</li>
                <li itemprop="recipeIngredient">1 cup unsalted butter, softened</li>
                <li itemprop="recipeIngredient">3/4 cup white sugar</li>
                <li itemprop="recipeIngredient">3/4 cup brown sugar</li>
                <li itemprop="recipeIngredient">2 large eggs</li>
                <li itemprop="recipeIngredient">2 teaspoons vanilla extract</li>
                <li itemprop="recipeIngredient">2 cups chocolate chips</li>
            </ul>
        </div>
        
        <div>
            <h4>Instructions:</h4>
            <div itemprop="recipeInstructions" itemscope itemtype="https://schema.org/HowToStep">
                <meta itemprop="position" content="1">
                <div itemprop="text">Preheat oven to 375°F (190°C)</div>
            </div>
            <div itemprop="recipeInstructions" itemscope itemtype="https://schema.org/HowToStep">
                <meta itemprop="position" content="2">
                <div itemprop="text">Mix flour, baking soda, and salt in a bowl</div>
            </div>
            <div itemprop="recipeInstructions" itemscope itemtype="https://schema.org/HowToStep">
                <meta itemprop="position" content="3">
                <div itemprop="text">Cream butter and sugars until light and fluffy</div>
            </div>
            <!-- Additional steps would go here -->
        </div>
        
        <div>
            <h4>Nutrition Information:</h4>
            <div itemprop="nutrition" itemscope itemtype="https://schema.org/NutritionInformation">
                <span itemprop="calories">150 calories</span> per cookie
            </div>
        </div>
    </div>
</body>
</html>

```

Microdata is a way to embed machine-readable data in HTML documents. It's particularly useful for SEO as it helps search engines understand the content of your pages more precisely.

### Key Microdata Attributes:

1. **`itemscope`**: Specifies that an element contains information about an item
2. **`itemtype`**: Specifies the type of item being described using a URL (typically from Schema.org)
3. **`itemprop`**: Specifies a property of the item

### Benefits of Microdata:

- **Rich Snippets**: Search engines may display additional information in search results
- **Better Understanding**: Search engines understand the content and context better
- **Voice Search**: Helps with providing accurate answers for voice searches
- **Specialized Results**: Content may appear in specialized search results (recipes, products, etc.)

### Schema.org Vocabulary:

The most common vocabulary for microdata is [Schema.org](https://schema.org/), which provides a collection of shared vocabularies that webmasters can use to mark up their pages.

Common Schema.org types include:
- Person
- Product
- Event
- Organization
- Recipe
- Movie
- Review
- LocalBusiness
- Article
- BreadcrumbList

