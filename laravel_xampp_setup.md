# Laravel Xampp Setup Window

## Install Xampp
Install Xampp from https://www.apachefriends.org/index.html

- Run the Xampp installer and open the Xampp control panel
- Make sure that you enable the Apache and MySQL services
- On mac you need to click "Start" on the Home tab, "Enable" on the Network tab and "Mount" on the Location Tab. Click "Explore" on the location tab to open your Xampp/Lampp folder

## Install Composer
Go to https://getcomposer.org/download

## Create a New Laravel Project With Composer

Open a terminal in the htdocs folder. htdocs is where all of your local projects go.

htdocs folder location:  
**Windows** - C:\Xampp\htdocs

```
composer create-project --prefer-dist laravel/laravel PROJECT_NAME
```
## Virtual Host Setup

Сreate a virtual host for your project

## Edit Hosts File

**Windows** - C:/Windows/System32/drivers/etc/hosts

Add these lines:

```
127.0.0.1	localhost
127.0.0.1	PROJECT_NAME.test

```

## Edit Virtual Hosts File

**Windows** - C:/xampp/apache/conf/extra/httpd-vhosts.conf
```
<VirtualHost *:80>
    DocumentRoot "C:/xampp/htdocs"
    ServerName localhost
</VirtualHost>

<VirtualHost *:80>
    DocumentRoot "C:/xampp/htdocs/PROJECT_NAME/public"
    ServerName PROJECT_NAME.test
 </VirtualHost>
```

### Restart Apache with the Xampp panel

Now visit http://laravel.test 

## If it does not work, make sure virtual hosts file is enabled in httpd.conf
- **Windows** - C:/xampp/apache/conf/httpd.conf

Remove the # from the beginning of this line

```
#Include etc/extra/httpd-vhosts.conf
```
Save the file

`git init`  
`git add .`  
`git commit –m "Comment"`  
**`git remote add origin https://github.com/SergeyHub/xampp_laravel_setup.git`**    
`git pull --rebase origin master`  
`git push -u origin master` 
