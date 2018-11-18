---
layout: post
title:  "ownCloud Quickstart"
date:   2018-11-17 18:00:00 -0500
---
# Quick Start: Installing and Using ownCloud

ownCloud is an open-source file sharing server that you control. With an ownCloud server you can store your private data, such as passwords, files, photos, music, movies, contacts, and calendar entries, and access it with devices such as Android and iPhone smartphones. ownCloud supports HTTPS and offers server-side encryption, so that you can securely share your data with other people and collaborate with them on documents. ownCloud synchronizes data, so that every device has the same data.

Here's how to install and configure the latest stable version of ownCloud server on a single machine running Red Hat Enterprise Linux (RHEL) 7; install the ownCloud desktop client on a MacOS desktop system; and connect from the client to the server for test and demonstration purposes. While ownCloud offers a range of installation options, these procedures describe a simple process for installing a Linux package and a desktop client.

These procedures assume that you're familiar with installing Linux distribution packages, and that you are running this LAMP stack:

* Red Hat Enterprise Linux 7 operating system
* Apache 2.4 web server
* SQLite
* PHP 5.6+ runtime

These procedures also assume a user familiar with installing MacOS packages.

**Note**: Before putting an ownCloud server into production, you will need to ensure that your system has the resources to support the traffic and ever-increasing volume of data that your users will require. For details on deployment, go to ["Deployment Considerations"](https://doc.owncloud.org/server/latest/admin_manual/installation/deployment_considerations.html) in the ownCloud Server Administration Manual.

## Installing the ownCloud Package

This procedure installs the latest stable `owncloud-files` Community Edition distribution package. Run the following shell commands as `root`.

1. Trust the ownCloud repository:

   ```# rpm --import https://download.owncloud.org/\```<br>
   ```download/repositories/production/RHEL_7/repodata/\```<br>
   ```repomd.xml.key```

2. Download the ownCloud package from the repository:

   ```# wget http://download.owncloud.org/download/\```<br>
   ```repositories/production/RHEL_7/ce:stable.repo \```<br>
   ```-O /etc/yum.repos.d/ce:stable.repo```

3. Install the ownCloud distribution package:

   ```# yum clean all```<br>
   ```# yum install owncloud-files```

You have installed the ownCloud package. Now you should run the installation wizard.

## Running the Installation Wizard

The installation wizard creates an administrator account for the ownCloud server. Defining administrator credentials is important to prevent a malicious actor from locking you out. Here's how to create an administrator account.

1. On the ownCloud server, open a web browser and enter this URL:

    ```http://localhost/owncloud```

   The ownCloud Setup page opens.

2. Enter the administrator username and password you want to use and click **Finish Setup**

   The administrator credentials are defined.

You can now use the ownCloud server.

For details on the installation wizard, including post-installation hardening steps, go to ["The Installation Wizard"](https://doc.owncloud.org/server/latest/admin_manual/installation/installation_wizard.html) in the ownCloud Server Administration Manual.

## Enabling Users to Connect to the ownCloud Server

For users to connect to your ownCloud server, they need the server's IP address and their account credentials. Here's how to create a user account with default values using the Web UI.

1. On the ownCloud User Management page, enter the new user's Login Name and initial Password and click **Create**

   The user information is added to the displayed list.

You can now provide the user with the ownCloud server address and these credentials.

For details on creating a user account, go to ["Creating a New User"](https://doc.owncloud.org/server/latest/admin_manual/configuration/user/user_configuration.html#creating-a-new-user) in the ownCloud Server Administration Manual.

## Installing an ownCloud Client

This procedure completes a standard default installation of the ownCloud client on a MacOS desktop system.

1. On the desktop, open a web browser and enter this URL:

   ```https://download.owncloud.com/desktop/stable/\```<br>
   ```ownCloud-2.5.1.10818.pkg```

   The ownCloud installer package file is downloaded to the Downloads folder.

2. In the Downloads folder, open the ownCloud installer package file.

   The ownCloud Client Installer starts.

3. Click **Continue**

   The installer gives you the option to change the installation location.

4. Click **Install**

   The installer prompts you for administrator credentials.

5. Enter your administrator credentials and click **Install Software**

   The package is installed, and you are prompted, "The installation was successful."

6. Click **Close**

   You are prompted to move the installer to the Trash.

7. Click **Move to Trash**

   The installer file is moved to the Trash.

You have installed the ownCloud desktop client.

For details on installing ownCloud desktop clients, go to <https://doc.owncloud.org/desktop/latest/>.

## Connecting to the ownCloud Server

Once your ownCloud server is installed, configured, and running, and a user's account is defined, that user can connect to it through a desktop or mobile client. Here's how to connect to an ownCloud server using an ownCloud MacOS desktop client.

1. From the Applications folder, open the owncloud application

   The ownCloud Connection Wizard opens:
   ![owncloud Connection Wizard window](/assets/ownCloud_Connection_Wizard.png "Connection Wizard")

2. Enter the server address and click **Next**

   The connection wizard prompts you to enter your user credentials.

3. Enter your username and password and click **Next**

   The connection wizard prompts you to set up local folder options.

4. Click **Connect** (this uses the default option of synching all of your files on the ownCloud server)

   The ownCloud Desktop Client icon appears on the menu bar.

The client is connected with the ownCloud server and begins synchronizing your files. 

For details on the ownCloud desktop client, go to <https://doc.owncloud.org/desktop/latest/navigating.html>.
