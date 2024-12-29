### **Web Component Display with Node.js Server**

#### **Description**
This program serves an HTML file displaying a styled book component through a Node.js server. The program performs the following tasks:

1. Creates and serves an HTML page styled with CSS.
2. Displays details of a book, including an image, title, author, and description.
3. Uses a Node.js server to serve the HTML page to clients.
4. Reads the HTML file dynamically from the `templates` directory and sends it as a response to client requests.

---

#### **Features**
- **HTML Styling:**  
  A visually appealing book component with:
  - Title and author details.
  - A centered image.
  - A brief description styled with custom fonts.

- **Dynamic HTML Serving:**  
  The Node.js server reads the HTML file dynamically from the `templates` folder and serves it on port 3000.

- **Modular and Organized Code:**  
  Uses the Node.js `http` and `fs` modules for file reading and serving content efficiently.

---

#### **Example**
When the server is running, navigating to `http://localhost:3000` displays the following content:

1. A header titled **"Book Component By Function"**.
2. An image of the book cover (e.g., _"You Don't Know JS: Scopes and Closures"_ by Kyle Simpson).
3. A brief description of the book content.
4. A footer with ©2021 credit.

**HTML Preview:**
```
---------------------------------------------------
| Book Component By Function                     |
|-----------------------------------------------|
|  (Book Cover Image Centered)                  |
|  By Kyle Simpson                              |
|  Parts of the language that many JavaScript   |
|  programmers simply avoid.                    |
---------------------------------------------------
|                 ©2021 Tania                   |
---------------------------------------------------
```

---

#### **How It Works**
1. **HTML Structure**:  
   - The HTML page (`page.html`) is stored in the `/templates` directory.
   - Styled with CSS to include flex layouts and font customizations.

2. **Node.js Server**:  
   - A server is created using the `http` module.
   - The `fs` module reads the HTML file and sends it to the client.
   - The server listens on port 3000.

---

#### **Programmers**
- אליאס דבאג  
- נור עמאר  

---

#### **Code**
```javascript
const http = require("http"); // Import Node.js core module
const fs = require("fs"); // import file module
const path = require("path");
const dirPath = path.join(__dirname, "/templates");

// read html file
const file2Send = fs.readFileSync(`${dirPath}/page.html`);

// creating server
const server = http.createServer(function (req, res) {
  // handle incoming requests here..
  console.log(req);
  // write http header
  res.setHeader("Content-Type", "text/html");
  // write html file to the client
  res.end(file2Send);
});

server.listen(3000); // listen for any incoming requests
console.log("Node.js web server at port 3000 is running.");
```

---

Let me know if you need further adjustments!
