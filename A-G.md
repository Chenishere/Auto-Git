# AutoGit project :
#### Projet infra de Yanice et Aymeric
---
#### L'objectif de ce projet d'infrastructur est de pouvoir heberger un sit web automatiquement et directement depuis Git !
![alt Autogit](https://logos-world.net/wp-content/uploads/2020/11/GitHub-Emblem.png)

---
**N°1 The first step is to Install nginx**
Go to the nginx conf file (here) :
```bash
(/etc/nginx/nginx.conf)
```
And change the root line to : `/var/www` and don't forget to restart your ngninx.
Next you had to create all the directories you will have in your git project, for exemple your `/assets` with 
```bash
mkdir {your file}
```
Now you need to create a new user and add him to the nginx group that already exist. 
```bash
useradd {Your user name}
sudo usermod -a -G nginx {Your user name}
```
So now you can give all the permissions (exept) to the nginx the directory and all his files with `chgrp nginx /var/www -R`
Now everything is good with nginx !
Now you have an access to your website with your server address on your browser !

---
**N°2 Now lets start with the ssh keys!**
So now you need to generate an ssh key pair with this command 
```bash
ssh-keygen -b 2048 -t rsa
```
Put your public ssh key in the file `authorized_keys`,and your private key in the github's secret as `SSH_PRIVATE_KEY`.

Congratulation !! You can now enjoy your automated deployment on your website server ! 


![alt Autogit](https://torrefacteur.co/wp-content/uploads/2017/05/applause.jpg)
