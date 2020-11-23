Wordpress with LDAP authentication test environment
used Vagrant and Ansible for deployment 

Here is test environment. After `vargant up` you will get next:
- Two virtual servers with Database and Webserver roles
- Mysql is installed and configured on `db` server
- Apache and Wordpress are installed and configured on `web` server
- Wordpress configured to use Test LDAP server https://www.forumsys.com/tutorials/integration-how-to/ldap/online-ldap-test-server/ 
- `serviceuser` configured to manage `mysql` and `apache`services via SystemD on both servers

Requirements:
- Linux machine (Ubuntu for example)
- Installed virtualbox
```
# apt install virtualbox
```
- Installed vagrant
```
wget https://releases.hashicorp.com/vagrant/2.2.14/vagrant_2.2.14_x86_64.deb
sudo dpkg -i ./vagrant_2.2.14_x86_64.deb
```

Using:
```
vagrant up
```
Connect to the http://192.168.1.2/wp-admin/ and login to wordpress with on of LDAP users (tesla:password for example)

Configuration mostly done with `group_vars/all` and `Vagrantfile`
