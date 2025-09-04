# EX01 Developing a Simple Webserver
## Date:30/08/2025

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

htmlcontent = '''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
 <font color="green" face="monospace" size="100">
            <h1 align="center"> <b> List of protocol in TCP/IP Model</b></h1>
        </font>
        <font color="red">
        <h2>
            Application Layer - HTTP, FTP, DNS, Telnet & SSH <br>
            Transport Layer - TCP & UDP <br>
            Network Layer - IPV4/IPV6 <br>
        </h2>
        </font>
</body>
</html>'''

class serverResponse(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(htmlcontent.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,serverResponse)
httpd.serve_forever()
```
## OUTPUT:
![
](<Screenshot 2025-09-04 104946.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
