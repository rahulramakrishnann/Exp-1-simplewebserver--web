# EX01 Developing a Simple Webserver

## Date: 07/10/2023

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top 5 Revenue Generating Companies<h1>
<UL TYPE=“circle”>
<LI> Amazon </LI>    
<LI> Tesla </LI>
<LI> TVS </LI>
<LI> Malbro </LI>
<LI> ITC </LI>
</UL>
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
server_address = ('',6969)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:

![image](https://github.com/rahulramakrishnann/simplewebserver/assets/143045415/d1810722-c326-49d3-8c37-a2101370839d)
![image](https://github.com/rahulramakrishnann/simplewebserver/assets/143045415/5f66b144-c5c1-468e-a24a-fd73c6cbec6c)

## RESULT:
The program for implementing simple webserver is executed successfully.
