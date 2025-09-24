# EX01 Developing a Simple Webserver
## Date: 24-09-2025

## AIM:
To develop a simple webserver to serve html pages and display the Device Specifications of your Laptop.

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
Name: Karthic V
Roll Number: 25005146


```
from http.server import HTTPServer,BaseHTTPRequestHandler
content="""
<!doctype html>
<html>
<head>
<title> My LAPTOP </title>
</head>
<body>
<h1><font color="green"><center>MY LAPTOP CONFIGURATION </center></font></h1>
<table border="4" cell pading="40" align="center">
<tr>
   <th>processor</th>
   <th>Intel(R) core(TM) ULTRA5 125H</th>
</tr>
<tr>
    <th>Installed RAM</th>
    <th>16.0 GB (usable 15.6)</th>
 </tr>
 <tr>
    <th>Version</th>
    <th>22H2</th>
 </tr>
 <tr>
    <th>System Type </th>
    <th>64-bit operating system,x64-based processor</th>
 </tr>
 <tr>
    <th>Edition </th>
    <th>Windows 11 Home single language</th>
 </tr>
 <tr>
    <th>pen & touch</th>
    <th>No pen or touch input is available for this display</th>
 </tr>
</table>
</body>
</html>
"""

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())
    

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
<img width="1917" height="869" alt="Screenshot 2025-09-24 154644" src="https://github.com/user-attachments/assets/badbecc6-daaf-4405-bd69-6305ced57593" />

![alt text](<Screenshot 2025-09-24 153407.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
