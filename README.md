![Screenshot_2025-05-30-14-14-34-76_320a9a695de7cdce83ed5281148d6f19 (1)](https://github.com/user-attachments/assets/3e70c5dd-c930-4ad7-a459-7fc678543bc6)# EX01 Developing a Simple Webserver

# Date:
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content="""
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1><center>My Laptop Configuration Details</center></h1>
   <table border="1" cellpadding="10" align="center">
        <tr>
            <th bgcolor="lightblue">Specification</th>
            <th bgcolor="lightgreen">Details</th>
        </tr>
        <tr>
            <td>Model</td>
            <td>Lenovo ThinkPad i5</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel Core i5</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>8GB</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>256GB SSD</td>
        </tr>
        <tr>
            <td>Graphics</td>
            <td>Integrated Intel UHD Graphics</td>
        </tr>
        <tr>
            <td>Display</td>
            <td>14-inch FHD (1920 x 1080)</td>
        </tr>
        <tr>
            <td>Operating System</td>
            <td>Windows 10</td>
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

               

    
# OUTPUT:

![Screenshot_2025-05-30-14-14-45-06_320a9a695de7cdce83ed5281148d6f19](https://github.com/user-attachments/assets/8c429062-5696-409a-bf59-d260c6e8a21d)

![Screenshot_2025-05-30-14-14-24-04_320a9a695de7cdce83ed5281148d6f19](https://github.com/user-attachments/assets/0e74e278-bfbe-452a-ba04-c1cea59a614d)


# RESULT:
The program for implementing simple webserver is executed successfully.
