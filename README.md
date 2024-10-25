Asterisk VoIP Server Configuration
This repository contains configuration files, setup scripts, and documentation to deploy an Asterisk-based VoIP server on an Ubuntu virtual machine instance. The Asterisk PBX enables real-time voice communications over IP networks (VoIP), allowing connectivity for SIP (Session Initiation Protocol) clients, such as Linphone, and handling secure communication for voice calls and other media.

Project Overview
The primary purpose of this project is to establish a fully functional, customizable VoIP server using Asterisk, which supports:

SIP Endpoints: Configuration for SIP endpoints to allow secure and reliable client registration and authentication.
RTP (Real-time Transport Protocol): Configuration of RTP traffic on the default Asterisk range (typically UDP ports 10000-20000) for optimal voice data transport.
User Authentication and Access Control: Setup for secure user account authentication with username and password combinations.
Context Management: Different contexts (such as internal, external, etc.) to manage call routing, permissions, and access for each endpoint.
This server is ideal for users looking to learn about VoIP technology, set up a small business telephony system, or experiment with custom PBX configurations.

Requirements
Operating System: Ubuntu (tested on 20.04 and 22.04 LTS)
Software: Asterisk PBX software (20.9.3 or above)
Dependencies: Packages such as libedit-dev, libjansson-dev, and others (full list in setup instructions below)
Google Cloud Platform (optional): This setup was tested on a GCP VM instance, but it can be adapted to other platforms.

Installation
1. Clone the Repository

2. Install Dependencies
Run the provided setup.sh script to install necessary dependencies:

3. Configure Asterisk
SIP Configuration: Edit sip.conf to add SIP endpoints, with appropriate user credentials and contexts.
RTP Configuration: Modify rtp.conf to define the RTP port range (default: 10000-20000).
Context and Dial Plan Configuration: Update extensions.conf to configure call routing and access control.

4. Start the Asterisk Service
To start Asterisk and load all modules:

Troubleshooting
SIP Client Authentication Issues: Ensure usernames and passwords match between sip.conf and client configuration.
Module Loading Errors: Use sudo asterisk -rx "module load <module_name>.so" to load missing modules.
Firewall Rules: Ensure UDP ports 5060 (SIP) and 10000-20000 (RTP) are open in the firewall.
Files
sip.conf: SIP client settings, user credentials, and transport configuration.
rtp.conf: RTP port range definition for voice communication.
extensions.conf: Dial plan and call routing configuration for different contexts.
setup.sh: Script for dependency installation and initial setup.
Usage Notes
This configuration has been tested with Zoiper, a popular open-source SIP client, which can be used to test and verify call routing and registration.

