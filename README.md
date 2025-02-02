# EX01 Developing a Simple Webserver
## Date:07.10.2023

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
<html>
     
      <title> Image Map </title>
      <body>
       <table border="1" cellspacing="5"  cellpadding="3">
            <caption> Top five Revenue Generating Software Companies</caption>
            <tr>
             
               <th>S.NO</th>  
               <th>COMPANY</th>                                                                                                                                      
               <th>REVENUE</th>
              </tr>
              <tr> 
               <td>1</td>  
               <td>Microsoft</td>
               <td>65 Billion</td> 
              </tr>
               
              <tr> 
               <td>2</td>  
               <td>oracle</td>
               <td>6.5 Billion</td> 
              </tr>

              <tr> 
               <td>3</td>  
               <td>ibm</td>
               <td>6.6Billion</td> 
              </tr>

              <tr> 
               <td>4</td>  
               <td>sap</td>
               <td>7.8 Billion</td> 
              </tr>

              <tr> 
               <td>5</td>  
               <td>symantec</td>
               <td>6.9 Billion</td> 
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
![request](request_ss.png)
![output](simple_web_ss.png)

## RESULT:
The program for implementing simple webserver is executed successfully.
