# EX01 Developing a Simple Webserver
# Date:15/03/2024
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

<html>
	<title>web page </title>
<body>
	<table border="3" cellspacing="10">
	<caption> Top five Revenue Generating Software Companies </caption>
	<tr>
		<th> S.NO </th>
		<th>Company </th>
		<th> Revenue </th>
	</tr>
	<tr>
	<td> 1 </td>
	<td> MICROSOFT </td>
	<td> 65 Billion </td>
	</tr>
	<tr>
	<td> 2 </td>
	<td> Oracle </td>
	<td> 29.6 billion </td>
	</tr>
	<tr>
	<td> 3 </td>
	<td> IBM </td>
	<td> 29.1 billion </td>
	</tr>
	<tr>
	<td> 4 </td>
	<td> SAP </td>
	<td> 6.4 billion </td>
	</tr>
	<tr>
	<td> 5 </td>
	<td> Symantec </td>
	<td> 5.6 billion </td>
	</tr>
	</table>
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
![1](https://github.com/Rajkiran276/simplewebserver/assets/147471453/204942a2-ff22-4fb3-b6dd-7d3f2f2763bf)
![2](https://github.com/Rajkiran276/simplewebserver/assets/147471453/96e38aa3-8ff9-431c-9629-938223983674)

## RESULT:
The program for implementing simple webserver is executed successfully.
