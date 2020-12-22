# Nextcloud template for zabbix monitoring.
I did it using this template https://github.com/y-u-r/nextcloud-zabbix/blob/master/README.md for Zabbix v5.2

Go to your nexcloud administrator account settings.<br>
Create application key on Security tab.<br>
Import this template to zabbix and assign it to your nextcloud host.<br>
Use nextcloud admin login and application key as values for inherited macroses.<br>

If everything is good you can view monitoring XML with url like:<br>
https://NEXCLOUDADMIN:NEXTCLOUDKEY@NEXTCLOUDHOST/ocs/v2.php/apps/serverinfo/api/v1/info<br>
Log off nextcloud before testing or use another browser or curl -s urlabove.<br>

If you use reverse proxy and expirience:<br>
  - About 30 seconds delay with curl<br>
  - Nextcloud shows warning about too many wrong login attempts on the login page<br>
  - You get 997 error with curl or redirected to login page in browser.<br>
  
Check that you've added your reverse proxy ip to confg.php like:<br>
'trusted_proxies' => ['172.18.0.1']<br>
If you use docker type 'ifconfig' and your proxy ip will be like 172.17.0.1 for default network or 172.XX.0.1 for custom.

<br>https://github.com/dvydruk/nextcloud-zabbix-monitoring
