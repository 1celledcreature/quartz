**How websites work

Two main components make up a website:
	Front end - The way a browser renders a website
	 Back End - A server that processes a request and comes back with a response

**HTML

- Websites are created using:
	- HTML - Builds the websites and defines the structure
	- CSS - Makes the sites look good (style)
	- Javascript - Implement features on a page using interactivity

Hyper Text Markup Language (HTML) is the language websites are written in. 
Elements (tags) are building blocks of the pages and tells the browser how to display the content on the page,

Example:
![[Pasted image 20250213213750.png]]

This HTML structure has the following components:
- **!Doctype html** - Tells the browser to use HTML5 to interperate the page
- **HTML** - The root element of the page
- **head** - Information about the page (eg page title)
- **body** - Defines the content. Only content inside the body is displayed on the page
- **h1** - defines a large heading
- **p** - defines a paragraph

Many other elements (tags) for different things. Tags for buttons, images and whatever else is on the page.

Tags contain attributes which are used to style elements (eg make a tag a different colour): <p class="bold-text">

src attribute is used on images to specify the location of the image: 
<img src="img/cat.jpg">

an element can have multiple attributes  e.g., <p attribute1="value1" attribute2="value2">

Elements can have ID attributes <p id="example"> which is unique to the element.
Unlike 'class' element, an element must have different ID's to identify them. They are used for styling and to identify Javascript.

JavaScript (JS) is one of the most popular coding languages in the world and allows pages to become interactive. HTML is used to create the website structure and content, while JavaScript is used to control the functionality of web pages - without JavaScript, a page would not have interactive elements and would always be static. JS can dynamically update the page in real-time, giving functionality to change the style of a button when a particular event on the page occurs (such as when a user clicks a button) or to display moving animations.

JavaScript is added within the page source code and can be either loaded within <script> tags or can be included remotely with the src attribute: <script src="/location/of/javascript_file.js"></script>

The following JavaScript code finds a HTML element on the page with the id of "demo" and changes the element's contents to "Hack the Planet" : document.getElementById("demo").innerHTML = "Hack the Planet";

HTML elements can also have events, such as "onclick" or "onhover" that execute JavaScript when the event occurs. The following code changes the text of the element with the demo ID to Button Clicked: <button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>Click Me!</button> - onclick events can also be defined inside the JavaScript script tags, and not on elements directly. 



Sensitive Data Exposure occurs when a website doesn't properly protect (or remove) sensitive clear-text information to the end-user; usually found in a site's frontend source code.

We now know that websites are built using many HTML elements (tags), all of which we can see simply by "viewing the page source". A website developer may have forgotten to remove login credentials, hidden links to private parts of the website or other sensitive data shown in HTML or JavaScript.

Sensitive information can be potentially leveraged to further an attacker's access within different parts of a web application. For example, there could be HTML comments with temporary login credentials, and if you viewed the page's source code and found this, you could use these credentials to log in elsewhere on the application (or worse, used to access other backend components of the site).

Whenever you're assessing a web application for security issues, one of the first things you should do is review the page source code to see if you can find any exposed login credentials or hidden links.

![[Pasted image 20250303204627.png]]



HTML Injection is a vulnerability that occurs when unfiltered user input is displayed on the page. If a website fails to sanitise user input (filter any "malicious" text that a user inputs into a website), and that input is used on the page, an attacker can inject HTML code into a vulnerable website.

Input sanitisation is very important in keeping a website secure, as information a user inputs into a website is often used in other frontend and backend functionality. A vulnerability you'll explore in another lab is database injection, where you can manipulate a database lookup query to log in as another user by controlling the input that's directly used in the query - but for now, let's focus on HTML injection (which is client-side).

When a user has control of how their input is displayed, they can submit HTML (or JavaScript) code, and the browser will use it on the page, allowing the user to control the page's appearance and functionality.

![[Pasted image 20250303210016.png]]

The image above shows how a form outputs text to the page. Whatever the user inputs into the "What's your name" field is passed to a JavaScript function and output to the page, which means if the user adds their own HTML or JavaScript in the field, it's used in the sayHi function and is added to the page - this means you can add your own HTML (such as a <h1> tag) and it will output your input as pure HTML.

The general rule is never to trust user input. To prevent malicious input, the website developer should sanitise everything the user enters before using it in the JavaScript function; in this case, the developer could remove any HTML tags.