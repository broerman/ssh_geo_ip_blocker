SSH Geo IP blocking by tcpwrapper
================================

This playbook installs geoipupdate from maxmind and configures tcpwrapper to block SSH connects from allowed countries. You have to register to maxmind.com to be able to upgrade the geoip database.  This playbook was tested on Debian/Ubuntu x86_64 and raspberry pi.

##### Preparations 

edit hosts file 

ajust **geoip_version** and other **vars** in deploy.yaml

##### Run 

Deploy to server1 

```bash
ansible-playbook -i hosts deploy.yaml --limit server1
```

##### Monitoring 

Login to server1 and watch activities.

```bash
tail -f /var/log/auth.log /var/log/geo_check.log
```

