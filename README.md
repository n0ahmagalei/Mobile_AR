# Mobile_AR

Simple augmented reality application, that hosts an HTML based server on a web browser. This application scans a marker of our choosing then displays a 3D model on top of it. We are still currently working on physical interaction with the 3D model. 

The finalized product will be able to do the following along with everything else that has been implemented already:
* Send out push notifications to alert users about new or related 3D models
* Functional Website to showcase different models
* Display a log of scanned QR codes and their related models
* Set up a local host server
  
# Setting up the HTTPS Server with a Self-Signed SSL Certificate
This guide is intended to show the end user how to generate a self-signed SSL certificate using SSL and run an HTTPS server using Node.js `http-server` module.

## Prerequistes
- [OpenSSL](https://www.openssl.org)
- [Node.js](https://nodejs.org/en/download) and npm
- `http-server` module. This is done by copy-pasting this line of code in your terminal:
  ```
  npm install -g http-server
  ```
  
## Steps
1. **Generate your SSL Certificate.**
   Run this command in your respective terminal/command prompt:
   ```
   bash openssl req -x509 -newkey rsa:4096 -keyout key.perm -out cert.pem -days 365 -nodes
   ```
   This command generates a unique and self-signed SSL certificate (`cert.pem`) and a private key (`key.pem`) in your current directory.
2. **Install `http-server`:**
   If you haven't already iinstalled the `http-server` module globally, you can do so using npm:
   ```
   bash npm install -g http-server
   ```
3. **Start HTTPS Server.**
   Run this command in order to start your HTTPS server:
   ```
   bash http-server -S -C cert.pem -K key.pem -p 8000
   ```
   What this command does is that it starts a HTTPS server on port 8000 using the generated SSL certificate (`cert.pem`) and a private key (`key.pem`).
4.**Accessing the Server**
   Once the server is up and running, you are able to access it via a web browser or make requests to it programmatically.

   Open your web browser and navigate too the following address: `https://localhost:8000` in order to access the server. Since this is currently using a self-signed certificate, your respective browser of choice may display a warning message about an insecure connection. Ignore this message and proceed so that you can properly access the page.

   If you're making requests programatically, make sure that you are able to handle SSL certificate verifications appropiately in your code.

## Notes
- Setup is currenly under development purposes and local testing at the moment. For production environments, I reccomend using a valid SSL certificate that's signed by a trusted Certificate Authority (CA).
- Always make sure that the security of your private key (`key.pem`) and SSL certifcate (`cert.pem`) is secure. Do not share them publically.

# Local Server Setup Guide
For development and testing of web applications, especially those that use technologies requiring server hosting (like AR.js), setting up a local server can be beneficial. This guide shows you how to easily run a local server using Python's built-in HTTP server module.

Prerequisites
* Before you begin, ensure that Python is installed on your machine:

Visit [python.org](https://www.python.org/downloads/) to download and install Python if it is not already installed.
Setting Up the Server
Follow these steps to start a local server using Python:

1. Open Your Command Line Interface
* Windows: Open Command Prompt or PowerShell.
* MacOS/Linux: Open Terminal.
2. Navigate to Your Project Directory
* Change to the directory containing your project files using the cd command:

```bash
cd path/to/your/project
```
3. Start the HTTP Server
* Run the following command in your command line interface:

For Python 3.x:

```
bash python3 -m http.server 8000
```

* This will start a server on port 8000. You can use any other free port by replacing 8000 with your preferred port number.

For Python 2.x (if still in use):

```
bash python -m SimpleHTTPServer 8000
```

4. Access Your Server
* Open a web browser and go to the following URL to access your project:

```
arduino http://localhost:8000
```
# Troubleshooting
Port Already in Use:
If you see an error that the port is already in use, try a different port number by changing 8000 in the command to another port number, such as 8080.

Firewall Issues:
Ensure that your firewall is not blocking access to the chosen port.

Additional Information:
This server is suitable for development and testing. For production environments, consider more robust server solutions like Apache or Nginx.

