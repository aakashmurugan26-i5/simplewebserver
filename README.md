# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

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
    <title>Laptop Configuration</title>
</head>

<body>
    <i>
    <h1 align="center">
        NAME : AAKASH M
    </h1>
    </i>
    <h3 align="center">REG NO : 26001770</h3>
    <h2 align="center">
        <i><u>Laptop Configuration</u></i>
    </h2>

    <table border="2" bgcolor="white"
           cellspacing="5" cellpadding="10"
           align="center" width="80%">
        <tr>
            <th bgcolor="lightblue" align="center">S.No</th>
            <th bgcolor="white" align="center">Device Type</th>
            <th bgcolor="lightblue" align="center">Device Info</th>
        </tr>

        <tr>
            <td bgcolor="lightblue" align="center">1</td>
            <td bgcolor="white" align="center">Device Name</td>
            <td bgcolor="lightblue" align="center">TL15-53M-G2</td>
        </tr>

        <tr>
            <td bgcolor="lightblue" align="center">2</td>
            <td bgcolor="white" align="center">Processor</td>
            <td bgcolor="lightblue" align="center">Intel(R) Core(TM) 5 210H (2.20 GHz)</td>
        </tr>

        <tr>
            <td bgcolor=lightblue align="center">3</td>
            <td bgcolor="white" align="center">Installed RAM</td>
            <td bgcolor="lightblue" align="center">16 GB (15.7 GB usable)</td>
        </tr>

        <tr>
            <td bgcolor="lightblue" align="center">4</td>
            <td bgcolor="white" align="center">Graphics Card</td>
            <td bgcolor="lightblue" align="center">Intel(R) Graphics (128 MB)</td>
        </tr>

        <tr>
            <td bgcolor="lightblue" align="center">5</td>
            <td bgcolor="white" align="center">Storage</td>
            <td bgcolor="lightblue" align="center">166 GB of 477 GB used</td>
        </tr>

        <tr>
            <td bgcolor="lightblue" align="center">6</td>
            <td bgcolor="white" align="center">Device ID</td>
            <td bgcolor="lightblue" align="center">5FD237C2-58EB-472A-99A2-E8822AB751E3</td>
        </tr>

        <tr>
            <td bgcolor="lightblue" align="center">7</td>
            <td bgcolor="white" align="center">Product ID</td>
            <td bgcolor="lightblue" align="center">00342-42954-11432-AAOEM</td>
        </tr>

        <tr>
            <td bgcolor="lightblue" align="center">8</td>
            <td bgcolor="white" align="center">System Type</td>
            <td bgcolor="lightblue" align="center">64-bit operating system, x64-based processor</td>
        </tr>

        <tr>
            <td bgcolor="lightblue" align="center">9</td>
            <td bgcolor="white" align="center">Pen and Touch</td>
            <td bgcolor="lightblue" align="center">No pen or touch input is available for this display</td>
        </tr>

    </table>

</body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Client request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my own webserver is running successfully...")
httpd.serve_forever()
```

## OUTPUT:
webpage
![alt text](<Screenshot (15).png>)

serverpage
![alt text](<Screenshot (16).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
