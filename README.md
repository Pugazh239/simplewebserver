# EX01 Developing a Simple Webserver


## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:

```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
  <head>
     <title>device specifications</title>
</head>
<body bgcolor="yellow">
    <h1 align="center">DEVICE SPECIFICATIONS</h1>
    <h3 align="center">Name:parveen sulthana</h3>
    <h3 align="center">Ref no:24900218</h3>
    <ol>
        <li>device name  :PARVEEN SULTHANA</li>
        <li>processor    :MAD RYZEN 5 5600H EITH RADEON GRAPHICS</li>
        <li>installed ram:8:00 GB (7.34GB USABLE)</li>
        <li>device id    :978DC2C7-56FA-</li>
        <li>product id   :00356-24679-30399-AAOEM</li>
        <li>system type   :64-bit operating system, x64-based processor</li>
        <li>pen and touch :No pen or touch input is available for this display</li>
    </ol>
    <hr>
    <ul>
        <li>edition</li>
        <li>version</li>
        <li>installed on</li>
        <li>os build</li>
        <li>experience</li>
    </ul>

</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:

<img width="1916" height="907" alt="image" src="https://github.com/user-attachments/assets/f2fae47e-3009-438f-8662-2e001f4ec19b" />

## RESULT:
The program for implementing simple webserver is executed successfully.
