# EX01 Developing a Simple Webserver
## Date:13/03/2024

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```C
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Webserver</title>
</head>
<body>
    <h1>Top 5 Revenue Companies</h1>
    <ol>
        <li>Apple</li>
        <li>Google</li>
        <li>Amazon</li>
        <li>Samsung</li>
        <li>TATA</li>
    </ol>
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
![6](https://github.com/Rajkiran2704/simplewebserver/assets/163234000/c6906b82-27c9-4401-91d5-7c5e53c3b593)
![7](https://github.com/Rajkiran2704/simplewebserver/assets/163234000/148e6bf3-6cc9-4f0f-8fde-3c5f63062617)
## RESULT:
The program for implementing simple webserver is executed successfully.
