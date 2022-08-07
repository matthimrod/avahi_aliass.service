# avahi_aliass.service
Simple conf.based avahi-alias service.

## Prerequisites
This is for linux systems that use avahi-daemon. This script requires `avahi-publish` which is part of the `avahi-utils` package, which can be installed by running the following on Debian-based disros:
```
apt install avahi-utils
```

## Setup

Copy the service file:
```
sudo cp avahi-alias@.service /etc/systemd/system
```
Change permissions and owner:
```
sudo chown root:root /etc/systemd/system/avahi-alias@.service
sudo chmod 644 /etc/systemd/system/avahi-alias@.service
```
Reload systemd to make the new service available:
```
sudo systemctl daemon-reload
```

## Usage
Setting up and removing aliases is as simple as the following:

### To add an MDNS CNAME Alias test.local:
```
systemctl enable --now avahi-alias@test.local.service
```

### To remove an alias:
```
systemctl disable avahi-alias@test.local.service
```
