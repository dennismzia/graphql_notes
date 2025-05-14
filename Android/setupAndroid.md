## this file details how to set-up Android emulator or device for pentesting

- Install user certificate and system certificates
- convert format of cacert.der to cacert.pem
```bash
openssl x509 -inform DER -in cacert.der -out cacert.pem
```


- use [proxy agent](https://github.com/GovTech-CSG/ProxyAgent) app to setup ie turn burp proxy on and off

-
``` bash
# Backup the existing system certificates to the user certs folder
cp /system/etc/security/cacerts/* /data/misc/user/0/cacerts-added/

# Create the in-memory mount on top of the system certs folder
mount -t tmpfs tmpfs /system/etc/security/cacerts

# copy all system certs and our user cert into the tmpfs system certs folder
cp /data/misc/user/0/cacerts-added/* /system/etc/security/cacerts/

# Fix any permissions & selinux context labels
chown root:root /system/etc/security/cacerts/*
chmod 644 /system/etc/security/cacerts/*
chcon u:object_r:system_file:s0 /system/etc/security/cacerts/*
```