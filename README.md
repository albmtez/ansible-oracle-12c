# ansible-oracle-12c

Configuration of a linux machine and Oracle Database 12c installation.

Supported version: 12.1.0.2

You must download these files from Oracle website:

- linuxamd64_12102_database_1of2.zip
- linuxamd64_12102_database_2of2.zip

And copy them into the roles/oracle-install/files directory.

A Vagrantfile is included, which allows to create a vm and install Oracle Database by simply executing:

```
vagrant up
```

Oracle Enterprise Manager Express is started and available in: `https://10.0.0.10:5500/em`