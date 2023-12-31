# Vagrant Virtual Machine Engineering Project COSC349
University of Otago COSC349 Cloud Architecture

## Windows Access
Due to a Vagrant issue, Vagrant functionality on a windows machine requires the Oracle VM Virtualbox Manager application be open.

## Project Description
This application aims to integrate the functionality of three seperate virtual machines in an expandable manner.
The program will provide a web interface, a backend database and an administrative user, each with a virtual machine hosting their respective functionality. The creation and integration of these machines is to represent the potential of virtualisation in portable software applications. 
This project will utilise Vagrant as an underlying technology to build and maintain these virtualised environments in a hypervisor-like manner.

## Application Specifications
The purpose of this application is to create an online web cache of interesting and useful websites. Access to this web server is to be delegated by a third party administrative user, and the data is to be hosted in a seperate standalone database server for the sake of keeping the web server light weight, and ensuring expansion capabilities.
## Prerequisites
Running this application requires the user have recent installations of the following programs:
- Vagrant
- Oracle VM VirtualBox Manager

## Application Running
Open a command prompt in the desired download location and run:

```git clone https://github.com/flari949/COSC349.git```

Run the VagrantFile using:

```vagrant up```

## Application Interaction
With the application running, the administrative, web, and database server virtual machines can be accessed as below:
#### Administrative Machine
Open a command prompt and ssh connect to the virtual machine using:

```vagrant ssh dbadmin```

Doing so will automatically open the database server with administrative privileges.
#### Web Server
Open an internet browser and navigate to:

```127.0.0.1:8080```

Doing so will prompt the user for a username and password. If verification credentials have not been set by the administrator, default username and password values are 'webuser1'. On credential verification the web server will display the database information. 

#### Database Server
A user, once their account has been created (with capabilities relative to set privileges), may access the database server through ssh by running the following on the command line:

```mysql -h 192.168.56.12 -u <username> -p```

Making sure to substitute ```<username>``` with a valid username and entering the correct password on prompt, the user will gain access to the MySQL database. 
