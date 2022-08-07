# avahi_aliass.service
Simple conf.based avahi-alias service.

Copy the `avahi-alias@.service` file to `/etc/systemd/system`. Setting up and removing aliases 
then becomes as simple as the following:

To add an MDNS CNAME Alias test.local:
```
systemctl enable --now avahi-alias@test.local.service
```

To remove:
```
systemctl disable avahi-alias@test.local.service
```
