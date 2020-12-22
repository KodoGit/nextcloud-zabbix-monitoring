# nextcloud template for zabbix monitoring.
Go to your nexcloud administrator account settings.<br>
Create application key on Security tab.<br>
Import this template to zabbix and assign it to your nextcloud host.<br>
Use nextcloud admin login and application key as values for inherited macroses.<br>

If everything is good you can view XML with url like:<br>
https://NEXCLOUDADMIN:NEXTCLOUDKEY@NEXTCLOUDHOST/ocs/v2.php/apps/serverinfo/api/v1/info<br>
Log off nextcloud before testing or use another browser or curl -s urlabove.<br>

If you use reverse proxy and expirience:<br>
  about 30 seconds delay with curl<br>
  Nextcloud shows warning about too many wrong login attempts on the login page<br>
do not forget to add your proxy ip in confg.php like:<br>
'trusted_proxies' => ['172.18.0.1']<br>
