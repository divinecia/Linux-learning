Introduction
This exam is divided into two parts, each worth 50% of your total grade. You will configure and secure systems in Part 1 and deploy and manage Docker services in Part 2. Your submission must include high-definition video recordings with a clear voiceover explaining each step, along with all required configuration files, source code, and supporting documentation.

 

Part 1: Network and Web Server Configuration
You are required to set up virtual interfaces, host web services on each interface, secure the server, and configure access restrictions.

 

Virtual Interface Configuration
Create two sub-interfaces/virtual interfaces on your Linux machine.
Assign static IP addresses in the same subnet as the original interface. Ensure the sub-interfaces are reachable by other VMs or host machines on the same network.
 

Host the AUCA Education Web Page
On the first virtual interface, configure an Apache2 web server to host a static web page advertising AUCA Education.
The domain name for this interface should be:
studentID.auca.ac.rw
Configure the web server and ensure the domain name resolves correctly.
 

Host a Dynamic Portfolio Page
On the second virtual interface, deploy a Dynamic Portfolio System that allows users to:

Select between Light and Dark themes for the portfolio.
Display personal information (profile picture, full name, profession, skills, etc.) fetched dynamically from a database.
Configuration Requirements:

Insert data manually into the database using SQL commands (no API required).
Use an Nginx web server to host the dynamic portfolio.
The domain name for this interface should be:
portfolio.auca.ac.rw
Ensure the system supports:

Switching between the Light and Dark themes on the frontend.
Dynamically retrieving and displaying portfolio information (e.g., profile picture, personal details, skills, and experience).
 

Security Configuration
HTTPs: Sign all both your hosted pages
Web Application Firewall (WAF):
Protect both the Apache and Nginx web servers using ModSecurity.
Firewall Configuration:
Allow only recognized IP addresses for SSH access.
Enable two-factor authentication (2FA) for SSH logins.
Permit only web traffic (HTTPS) and block all other traffic, except for whitelisted IP addresses.
Configure UFW to:
HTTPS Configuration:
Sign both hosted pages (AUCA Education & Portfolio CRUD System) with self-signed certificates as per Mini-Project #3 self-signing instructions.
Sign them using SSL/TLS encryption. Use a self-signed certificate or Let's Encrypt to ensure the page is served securely over HTTPS.
Validation:
Verify that both web services are secure, accessible via their respective domain names, and protected against unauthorized access.
 

Part 2: Docker Deployment with Traefik Load Balancing
You will deploy the Portfolio CRUD system using Docker containers and implement load balancing with Traefik.

 

Docker Setup
Build Docker images for the Dynamic Portfolio System, ensuring:
The image names include your Student ID.
Both the frontend and database are containerized and function correctly.
 

Traefik Load Balancer
Set up Traefik as a load balancer for the Docker containers.
Configure Traefik to:
Distribute traffic across multiple Docker nodes.
Host nodes running on Ubuntu and CentOS/RedHat servers.
Ensure high availability:
The system must remain functional as long as at least one node is operational.
 

Security Implementation
TLS Encryption:
Configure Traefik to use Let's Encrypt for HTTPS traffic.
Access Control:
User authentication and authorization.
API key-based access for specific functionalities.
Implement at least two security mechanisms for the Portfolio system, such as:
