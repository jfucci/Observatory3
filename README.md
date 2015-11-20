Observatory3
============

[![Build Status](https://travis-ci.org/rcos/Observatory3.svg?branch=master)](https://travis-ci.org/rcos/Observatory3)

A project tracking dashboard for Rensselaer Center for Open Source. A ground up rewrite.

Working to replace a system with these [features](docs/Legacy_Features.md).
See our [planned feature set.](docs/Feature_Requirements.md)

Features
--------

Observatory is a powerful dashboard tracking open source projects and contributors that are built through Rensselaer Center for Open Source. The current implemenation can be seen in action at [rcos.io](http://rcos.io). We are a highly active community of open source developers that attend school at Rensselaer.

Key Features Include

- Project Tracking
- Individual Progress reports
- Attendance system for users
- Information gathering and blog platform for projects

Installation
------------

### Recommended Method (using Vagrant):  
1. Download and install Vagrant and Virtualbox  
2. Run the following to create and run a virtual machine with our development environment:

    ```shell
    git clone https://github.com/rcos/Observatory3.git
    cd Observatory3
    vagrant up
    ```

3. To get a shell on that virtual machine, run the following:

    ```shell
    vagrant ssh  
    ```
All the code is located in /vagrant.

### Manual Method:  
1. Install nodejs (nodejs-legacy for debian-based distributions), npm, ruby, and Mongo DB
2. Install global node dependencies:

    ```shell
    npm install -g grunt-cli grunt bower
    ```

3. Install sass:

    ```shell
    sudo gem install sass
    ```

4. Clone the repository and install local node dependencies:

    ```shell
    git clone https://github.com/rcos/Observatory3.git
    cd Observatory3
    npm install
    ```
    
    If the last command gave errors, try the following:

    ```shell
    sudo chown $USER -R ~/.npm
    npm install
    ```

5. Start the mongodb service:

    ```shell
    sudo service mongodb start # or equivalent if not on an ubuntu-based distribution
    ```
    If mongodb fails to start, run the following and try again:

    ```shell
    sudo mkdir -p /data/db
    ```

Running
-------

Use the following command from /vagrant if logged into the Vagrant virtual machine or from the project directory otherwise:

```
grunt serve
```

Grunt will run the server and make the project available at [http://localhost:9000](http://localhost:9000). 

Want to develop with us? Check out the generator we use at [here](https://github.com/DaftMonk/generator-angular-fullstack). 
