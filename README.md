# EX01 Developing a Simple Webserver
## Date: 26-02-2024

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
<title> Top Five Revenue Generating Software Companies </title>
<body bgcolor="grey">
      <h2 align="center">Top Five Revenue Generating Software Companies</h2> 
<table border="4" align="center" >
<tr>
 <td>RANK</td>
 <td>COMPANY</td>
 <td>REVENUE</td>
</tr>
<tr>
 <td>1</td>
 <td>Microscoft</td>
 <td>57.9</td>
</tr>
<tr>
 <td>2</td>
 <td>Oracle</td>
 <td>21.0</td>
</tr>
<tr>
 <td>3</td>
 <td>SAP</td>
 <td>16.1</td>
</tr>
<tr>
 <td>4</td>
 <td>Computer Associates</td>
 <td>4.2</td>
</tr>
<tr>
 <td>5</td>
 <td>Adobe</td>
 <td>3.4</td>
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
![alt text](<Screenshot 2024-03-12 112904.png>)
![alt text](<Screenshot 2024-03-12 112945-1.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
