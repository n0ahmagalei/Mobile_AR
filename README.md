# Mobile_AR

Simple augmented reality application, that hosts an HTML based server on a web browser. This application scans a marker of our choosing then displays a 3D model on top of it. We are still currently working on physical interaction with the 3D model. 

The finalized product will be able to do the following along with everything else that has been implemented already:
* Send out push notifications to alert users about new or related 3D models
* Functional Website to showcase different models
* Display a log of scanned QR codes and their related models
* Set up a local host server

# Local Server Setup Guide
For development and testing of web applications, especially those that use technologies requiring server hosting (like AR.js), setting up a local server can be beneficial. This guide shows you how to easily run a local server using Python's built-in HTTP server module.

Prerequisites
* Before you begin, ensure that Python is installed on your machine:

Visit python.org to download and install Python if it is not already installed.
Setting Up the Server
Follow these steps to start a local server using Python:

1. Open Your Command Line Interface
* Windows: Open Command Prompt or PowerShell.
* MacOS/Linux: Open Terminal.
2. Navigate to Your Project Directory
* Change to the directory containing your project files using the cd command:

bash
Copy code
cd path/to/your/project
3. Start the HTTP Server
* Run the following command in your command line interface:

For Python 3.x:

bash
Copy code
python3 -m http.server 8000
* This will start a server on port 8000. You can use any other free port by replacing 8000 with your preferred port number.

For Python 2.x (if still in use):

bash
Copy code
python -m SimpleHTTPServer 8000
4. Access Your Server
* Open a web browser and go to the following URL to access your project:

arduino
Copy code
http://localhost:8000
Troubleshooting
Port Already in Use: If you see an error that the port is already in use, try a different port number by changing 8000 in the command to another port number, such as 8080.
Firewall Issues: Ensure that your firewall is not blocking access to the chosen port.
Additional Information
This server is suitable for development and testing. For production environments, consider more robust server solutions like Apache or Nginx.

