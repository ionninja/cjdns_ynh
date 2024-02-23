# Setup your website on cjdns network

1. From the Applications menu, first install wordpress and then "cjdns". 
2. Obtain your cjdns IPv6 address by navigating to Tools -> Logs -> Click on "Install the 'cjdns' app." Your IPv6 address should be displayed in the log.
3. Reboot your YunoHost server to make the tun device available. Navigate to Tools->Shutdown and click Reboot.
4. Navigate to Tools -> Yunohost Settings -> Security, and under NGINX, disable "Force HTTPS." Click Save to apply the changes.
5. Finally edit `/etc/nginx/conf.d/[your-domain].conf`, add your cjdns-ipv6 to the list of `server_name`. 
