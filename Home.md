Welcome to the FusionInvoice-FOSS wiki!

Installation Prerequisites:
* A web server of some sort - Apache, nginx, etc.
* PHP >= 7.0.0
* OpenSSL PHP Extension
* PDO PHP Extension
* Mbstring PHP Extension
* Tokenizer PHP Extension
* XML PHP Extension
* DOM PHP Extension
* iconv PHP Extension
* Fileinfo PHP Extension (only if using the data import module)
* MySQL or MariaDB
* A modern and updated web browser

Composer installed
Here is a good link with composer installation instructions for Ubuntu 18.04:
[Composer Install instructions](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-18-04)

Sample Apache2 virtual host conf:

FusionInvoiceFOSS.conf

	<VirtualHost *:80>
		ServerAdmin webmaster@localhost

		DocumentRoot /var/www/FusionInvoiceFOSS/public
		ServerName FusionInvoiceFOSS
		ServerAlias FusionInvoiceFOSS
		<Directory />
			Options FollowSymLinks
			AllowOverride All
		</Directory>
		<Directory /var/www/FusionInvoiceFOSS/public/>
			Options Indexes FollowSymLinks MultiViews
			AllowOverride All
			Order allow,deny
			allow from all
		</Directory>

		ScriptAlias /cgi-bin/ /usr/lib/cgi-bin/
		<Directory "/usr/lib/cgi-bin">
			AllowOverride None
			Options +ExecCGI -MultiViews +SymLinksIfOwnerMatch
			Order allow,deny
			Allow from all
		</Directory>

		ErrorLog ${APACHE_LOG_DIR}/error.log

		# Possible values include: debug, info, notice, warn, error, crit,
		# alert, emerg.
		LogLevel warn

		CustomLog ${APACHE_LOG_DIR}/access.log combined

	    Alias /doc/ "/usr/share/doc/"
	    <Directory "/usr/share/doc/">
		Options Indexes MultiViews FollowSymLinks
		AllowOverride None
		Order deny,allow
		Deny from all
		Allow from 127.0.0.0/255.0.0.0 ::1/128
	    </Directory>


	</VirtualHost>
