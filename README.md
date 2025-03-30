# EX01 Developing a Simple Webserver
## Date: 30/03/2025
## AIM:

To develop a simple webserver to serve html pages and display the configuration details of laptop.
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
## ROGRAM:

from django.shortcuts import render,HttpResponse
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Webserver</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background: #f4f4f4;
            text-align: center;
            padding: 20px;
        }

        header {
            font-size: 32px;
            font-weight: bold;
            margin-bottom: 20px;
            color: #007aff;
        }

        table {
            width: 50%;
            margin: 20px auto;
            border-collapse: collapse;
            background: rgba(255, 255, 255, 0.8);
            box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.1);
            border-radius: 12px;
            overflow: hidden;
            backdrop-filter: blur(10px);
        }

        th, td {
            border: 1px solid rgba(0, 0, 0, 0.2);
            padding: 15px;
            text-align: left;
        }

        th {
            background: rgba(0, 122, 255, 0.8);
            color: white;
        }

        .multiplication-table {
            margin-top: 20px;
            font-size: 20px;
            color: #333;
            background: rgba(255, 255, 255, 0.9);
            padding: 15px;
            width: 40%;
            margin-left: auto;
            margin-right: auto;
            border-radius: 12px;
            box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
        }
    </style>
</head>
<body>
    <header>Webserver</header>
    
    <table>
        <tr>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Age</th>
            <th>Reference Number</th>
        </tr>
        <tr>
            <td>N V MOHANA</td>
            <td>KRISHNA</td>
            <td>18</td>
            <td>24000587</td>
        </tr>
        <tr>
            <td>KRISHNA </td>
            <td>RAJ</td>
            <td>18</td>
            <td>24000588</td>
        </tr>
    </table>

    <div class="multiplication-table">
        <h2>Table of 34</h2>
        <p>34×1=34</p>
        <p>34×2=68</p>
        <p>34×3=102</p>
        <p>34×4=136</p>
        <p>34×5=170</p>
        <p>34×6=204</p>
        <p>34×7=238</p>
        <p>34×8=272</p>
        <p>34×9=306</p>
        <p>34×10=340</p>
    </div>
</body>
</html>

'''
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
serveraddress=('',8000)
httpd = HTTPServer(serveraddress,Myserver)
httpd.serve_forever()


## OUTPUT:
![WhatsApp Image 2025-03-30 at 23 52 24_3f57fb3d](https://github.com/user-attachments/assets/2769f225-f20f-4b5b-ab0f-79b0851f47f1)


## RESULT:
The program for implementing simple webserver is executed successfully.
