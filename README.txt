# LAMP FCGI and wordpress configuration buildout
# ===============================================
# 
# This buildout configures a LAMP virtual host with fcgi and a user driven mysql
# database server. It's tested with Debian 6.0 and Ubuntu 10.4. 
# The configuration is fully contained within this buildout. Hostnames, ports
# and common options can be changed in the buildout sections at the top of
# of this file.
# 
# Apparmor users (ubuntu): mind adding the new mysql database path.
#
# Supervisord starts the mysql server. You can manually start the mysql server with 
# sudo -u username bin/mysqld_safe_run_as_user.
 
# Install
# ----------
#
# Install depencencies:
#    $ aptitude install git wget python libapache2-mod-fcgid php5-cgi apache2 apache2-mpm-worker apache2-suexec mysql-server-5.1
#
# Load apache modules:
#    $ a2enmod fcgid
#    $ a2enmod suexec  
# 
# Change the configuration in buildout-development.cfg to your needs or better make a new buildout config file.
#
# To run the buildout do the following as root:
#    $ cd /var/www
#    $ mkdir buildout_dir
#    $ cd buildout_dir
#    $ python bootstrap.py
#    $ bin/buildout -c buildout-development.cfg
# To start mysql run:
#    $ bin/supervisorctl start mysql
#
# Update
# -------------
#
# To change the configuration edit the main buildout file (buildout-development) and the config template files (./templates).
# Then rerun the buildout:
#    $ bin/buildout -Nc buildout-develpment.cfg 
# You could change the generated config files directly, but all changes are lost if you run buildout again. 
#                          
# Generated config files
# ----------------------
#
# etc/vhost.conf
# etc/php.ini
# parts/supervisor/supervisor.conf
# parts/logrotate.conf
# htdocs/wp-conifg.php
 
