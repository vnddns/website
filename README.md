# FAQs

## Where is my ip?
Your IP is hosted on a private ovh server.
The IP is not used for any other purpose than to offer the service.

## Is VN.AL private?
Yes, VN.AL is 100% private, we do not use your information for any other purpose than to offer you the service.

# Usage
You can simply login to the website and manage your subdomain and IP address there or you can use the simple HTTP API to update your IP with a script or dynamic DNS client.

### Cron
The easiest way to keep your mapping up to date is to add the following line to your crontab which will update your IP every three hours:
```
0 */3 * * * curl -u 'USERNAME:PASSWORD' https://vn.al/update
```

### ddclient
You can use [ddclient](https://github.com/ddclient/ddclient) to keep your IP address up to date with the following config:
```
server=vn.al, \
protocol=dyndns2,   \
login=USERNAME,     \
password=PASSWORD   \
SUBDOMAIN.vn.al
```

### DD-WRT
Routers running DD-WRT can update your IP address by using the built in dynamic DNS settings found under Setup &rarr; DDNS. Other routers may also work but are untested.
```
DDNS Service: Custom
DYNDNS Server: vn.al
Username: USERNAME
Password: PASSWORD
Hostname: SUBDOMAIN.vn.al
URL: /nic/update?hostname=
```
