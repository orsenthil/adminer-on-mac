Using Adminer On Mac
====================

Adminer is a excellent tool for viewing and working with Databases.
If you are on Mac, I dare say that it is better that SequelPro (the most loved client by Mac users).

How to install Adminer on Mac
=============================

Goal
----

We will install adminer with the goal of accessing it at


	http://apache.local/adminer.php


## Determine your Apache folder. On Mac, it is:

	/Library/WebServer/Documents/

## Download Adminer From https://www.adminer.org/#download


	curl -O https://github.com/vrana/adminer/releases/download/v4.2.5/adminer-4.2.5-mysql.php


## Move to appropriate folder


	sudo mv adminer-4.2.5-mysql.php /Library/WebServer/Documents/


## Add a theme


	curl -O https://raw.githubusercontent.com/pappu687/adminer-theme/master/adminer.css
	sudo mv adminer.css /Library/WebServer/Documents/


## Setup VirtualHosts


	sudo mkdir /etc/apache2/vhosts


##  Create a file called `apache.local.conf` at `/etc/apache2/vhosts` with the contents
	

	<VirtualHost *:80>
	    DocumentRoot "/Library/WebServer/Documents"
	    ServerName apache.local
	</VirtualHost>


##  Edit `/etc/hosts` and include


	127.0.0.1   apache.local


That's it!

Result
------

Here is how mine looks

![Adminer](https://dl.dropbox.com/s/7lm0jqkfh0794j6/Screenshot%202016-11-17%2018.16.54.png)

