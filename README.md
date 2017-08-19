# modsecurity-whitelist-apps

> As of 2017-08-19 this project is mostly outdated. Also the OWASP 3.* Ruleset now includes exclusions for Drupal and WordPress so I would recommend using those for Drupal and Wordpress instead of this project.

These configuration files are for disabling certain ModSecurity OWASP CRS 2.2.9 and 3.0.0 and Trustwave Commercial ModSecurity rules that cause false positives with certain web applications. The goal is to disable any incompatible rules with popular web applications like Wordpress and Drupal.

Please note that there may still be a lot of false positives. If you have a public web application to test with, your contributions to this would be appreciated!

<h2>To load the rules in Apache:</h2>

1. Download the rules into a directory on your server. For example: /etc/httpd/conf.d/modsecurity-whitelist-apps
2. Enabled the whitelist by adding a ModSecurity include statement to your ModSecurity config file. For example: Include /etc/httpd/conf.d/modsecurity-whitelist-apps/*.conf

<h2>To load the rules in cPanel Apache:</h2>

For EasyApache 4.x download the rules to your modsecurity configuraiton folder (Default in cPanel /usr/local/apache/conf):
```text
cd /etc/apache2/conf.d/
git clone https://github.com/wrender/modsecurity-whitelist-apps
```

Include the rules in the bottom of your modsec2.user.conf file by editing the file and adding the following include line:
``` text
# Add the whitelist files to ModSecurity
Include /etc/apache2/conf.d/modsecurity-whitelist-apps/*.conf
```


Restart the Web Server:
``` text
service httpd restart
```

---------------------------------

