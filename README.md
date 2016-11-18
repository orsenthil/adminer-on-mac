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


1. Determine your Apache folder. On Mac, it is:


	/Library/WebServer/Documents/


2. Download Adminer From https://www.adminer.org/#download


	curl -O https://github.com/vrana/adminer/releases/download/v4.2.5/adminer-4.2.5-mysql.php


3. Move to appropriate folder


	sudo mv adminer-4.2.5-mysql.php /Library/WebServer/Documents/


4. Add a theme


	curl -O https://raw.githubusercontent.com/pappu687/adminer-theme/master/adminer.css
	sudo mv adminer.css /Library/WebServer/Documents/


5. Setup VirtualHosts


	sudo mkdir /etc/apache2/vhosts


6.  Create a file called `apache.local.conf` at `/etc/apache2/vhosts` with the contents
	

	<VirtualHost *:80>
	    DocumentRoot "/Library/WebServer/Documents"
	    ServerName apache.local
	</VirtualHost>


7.  Edit `/etc/hosts` and include


	127.0.0.1   apache.local


That's it!
