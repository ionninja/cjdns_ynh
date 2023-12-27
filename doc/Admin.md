# Setup your website on cjdns network

1. In the Applications menu, search for "cjdns" and install it. 
2. Obtain your cjdns IPv6 address by navigating to Tools -> Logs -> Click on "Install the 'cjdns' app." Your IPv6 address should be displayed in the log.
3. Reboot your YunoHost server to make the tun device available. Navigate to Tools->Shutdown and click Reboot.
4. Navigate to Tools -> Yunohost Settings -> Security, and under NGINX, disable "Force HTTPS." Click Save to apply the changes.
5. Edit `/etc/nginx/conf.d/[your-domain].conf`, add your cjdns-ipv6 to the list of `server_name`. 
6. Finally, to allow public access for cjdns requests to your new wordpress site you can do the following:
   1.  SSH into your yunoHost server
   2.  Copy current sso configuration file to persistent: `cp /etc/ssowat/conf.json /etc/ssowat/conf.json.persistent`
   3.  Then edit the persistent file: `nano /etc/ssowat/conf.json.persistent`
   4.  Change `public` to `true` and add this line under the `wordpress.main uris` section: `"re:^.fc.*"`. Remember to add a trailing “,” to the above entry. For example:

```json
"wordpress.main": {
    "auth_header": true,
    "label": "WordPress",
    "public": true,
    "show_tile": true,
    "uris": [
        "example.nohost.me/blog",
        "re:^.fc.*"
    ],
    "use_remote_user_var_in_nginx_conf": false,
    "users": []
}
``````
