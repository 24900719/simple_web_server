# EX01 Developing a Simple Webserver

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

# PROGRAM:from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html lang="en">
<head>
    <title>System Configuration</title>
</head>
<body>
    <div class="container">
        <h1>SYSTEM CONFIGURATION</h1>
        <div class="specifications">
            <h2>System Configuration</h2>
            <ul>
                <li><span>Processor:</span> Intel Core i7-1360P (13th Gen)</li>
                <li><span>Operating System:</span> Windows 11 Pro</li>
                <li><span>Memory (RAM):</span> 16GB DDR4</li>
                <li><span>Storage:</span> 512GB SSD</li>
                <li><span>Graphics:</span> Integrated Intel Iris Xe Graphics</li>
                <li><span>Display:</span> 16" WUXGA (1920x1200), Anti-glare</li>
                <li><span>Battery:</span> 57Wh, Up to 8 hours</li>
                <li><span>Weight:</span> Approx. 1.7 kg (3.7 lbs)</li>
                <li><span>Ports:</span> USB-C, USB 3.2, HDMI, Audio Combo Jack, Ethernet</li>
                <li><span>Connectivity:</span> Wi-Fi 6, Bluetooth 5.2</li>
            </ul>
        </div>
    </div>
</body>
</html>
'''

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
# OUTPUT:
![image](https://github.com/user-attachments/assets/8ece7dcd-1215-4bb3-8483-fe0f09c5fadf)
![image](https://github.com/user-attachments/assets/ecdbbf21-7d86-449e-b093-3f84d3089d92)

# RESULT:
The program for implementing simple webserver is executed successfully.
