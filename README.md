
In this workshop, we'll go over creating a very basic web server in Node.js.
We'll open a port to listen, read a file from the system, and serve that back to a web browser.

# Networking Basics

It's helpful to know about the following ideas before starting. We'll talk about:

1. Servers
2. Ports
3. IP Addresses + DNS
4. HTTP
5. IO operations

# Getting Setup

Make sure you have node.js installed, as well as an editor (and, obviously, a browser).
The best way to do this is highly system dependent:

1. On Mac, you probably want to use brew.
2. I've never done Node.js on Windows, so I would guess that you'd download the windows installer
3. On Linux, you probably want to use yum or apt-get

# Writing the Code

1. First, copy the following snippet into your editor and save as index.js:

```javascript
const http = require('http')
const port = 3000

const requestHandler = (request, response) => {
  console.log(request.url)
  response.end('Hello HackWHS!')
}

const server = http.createServer(requestHandler)

server.listen(port, (err) => {
  if (err) {
    return console.log('Error: ', err)
  }

  console.log(`Listening on ${port}`)
})
```

run as node index.js

2. Spend some time playing around with this.

3. Next, create a file you want to serve. If you know HTML, maybe create an HTML file. Otherwise,
   just some text will do.

4. Challenge: how do you get the server to serve the file?
   Hint: in Node.js, processing is asynchronous. You'll send the response in the file-read handler.

