Hometask #1 (12/09)
===================

1. Create repo hometask1 (do not forget .gitignore)
2. Create Vagrantfile 
3. Centos 7
4. Provision Nginx server 
5. Forward port 80 → 8888
6. Place site content to `~/www-content` (*)
7. Push your project to github (and add user sko-lv as colaborator)
```bash
Commands to install nginx on Centos:
yum install -y epel-release
yum install -y nginx
rm -fr /usr/share/nginx/html/*
cp -rav /vagrant/www-content/* /usr/share/nginx/html

setenforce 0
sed -ie 's/^SELINUX=.*$/SELINUX=disabled/' /etc/selinux/config
cat /etc/selinux/config
systemctl start nginx
systemctl enable nginx
```

Success criteria
----------------
1. `vagrant up`
2. In your browser goto `localhost:8888`
3. See content placed to `~/www-content` (*)
