# Zabbix template for Nextcloud monitoring.
No scripts and agent settings!<br>
I did it using Zabbix v5.2 and this template https://github.com/y-u-r/nextcloud-zabbix/blob/master/README.md 

# Install
1. Go to your Nexcloud administrator account settings.<br>
2. Create application key on Security tab.<br>
3. Import this template into Zabbix server and assign it to your Nextcloud host.<br>
4. Change values of inherited macroses using Nextcloud login and application key<br>

# Manual test
If everything is good you can view monitoring XML with url like:<br>
https://NEXCLOUDADMIN:NEXTCLOUDKEY@NEXTCLOUDHOST/ocs/v2.php/apps/serverinfo/api/v1/info<br>
Log off Nextcloud before testing or use another browser or curl -s urlabove.<br>

# Troubleshoot
If you use reverse proxy and experience:<br>
  - About 30 seconds delay with curl<br>
  - Nextcloud shows warning about too many wrong login attempts on the login page<br>
  - You get 997 error with curl or redirected to login page in browser.<br>
  
Check that you've added your reverse proxy ip to confg.php like:<br>
'trusted_proxies' => ['172.18.0.1']<br>
If you use docker type 'ifconfig' and your proxy ip will be like 172.17.0.1 for default network or 172.XX.0.1 for custom.

<br>https://github.com/KodoGit/nextcloud-zabbix-monitoring
