xvfb-initscript
===============

XVFB Init Scripts


Sample debian-style init script for XVFB (X Virtual Frame Buffer).

Configuration is under `/etc/default/xvfb

Tested on Ubuntu LTS 14.04 64bit



Instructions:
-------------

Install required packages:

	
	sudo apt-get install xvfb
	

Initialize users and dirs:
	
	sudo groupadd -r xvfb
	sudo useradd -r -s /usr/sbin/nologin -g xvfb -G xvfb xvfb

Git clone this repository (optional):

		cd /tmp/

		git clone git@github.com:davidedg/xvfb-initscript.git
	or
		git clone https://github.com/davidedg/xvfb-initscript.git
		

Copy default config and init script from repo:

	
	sudo cp -a xvfb-initscript/etc/init.d/xvfb /etc/init.d/
	sudo chmod +x /etc/init.d/xvfb
	sudo cp -a xvfb-initscript/etc/default/xvfb /etc/default/
	sudo chown root.root /etc/default/xvfb
	sudo chown root.root /etc/init.d/xvfb
	sudo chmod 0755 /etc/init.d/xvfb
	

Install services on boot:

	
	sudo update-rc.d xvfb defaults
	sudo service xvfb start
	

Start Xvfb Daemon:

	
    sudo service xvfb start
	

Test with a program:

	. /etc/default/xvfb
	export DISPLAY=$XVFBDISPLAY ; firefox
	export DISPLAY=$XVFBDISPLAY; import -window root /tmp/screenshot.png

The import command is from imagemagick


