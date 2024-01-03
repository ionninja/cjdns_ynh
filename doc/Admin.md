# Setup your website on cjdns network

1. In the Applications menu, search for "cjdns" and install it. 
2. Copy your cjdns ipv6 that is shown when installation completes.
3. Navigate to Tools -> Yunohost Settings -> Security, and under NGINX, disable "Force HTTPS." Click Save to apply the changes.
5. Edit `/etc/nginx/conf.d/[your-domain].conf`, add your cjdns-ipv6 to the list of `server_name` inside square brackets [<cjdns-ipv6>] and make sure to remove any leading 0 from the address sections. 
6. Finally, restart nginx and you should be able now to access your wordpress site on the cjdns network.
