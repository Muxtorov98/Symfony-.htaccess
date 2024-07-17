# Symfony Project

This is a Symfony project. Below you will find the necessary configuration for the `.htaccess` file to redirect all traffic to `public/index.php`.

## .htaccess Configuration

Create or update the `.htaccess` file in the root of your project with the following content:

```
Options +FollowSymLinks
IndexIgnore */*
RewriteEngine on

# Redirect any request that does not start with /public
RewriteCond %{REQUEST_URI} !^/(public)
RewriteRule (.*) /public/$1

# If the request is within /public
RewriteCond %{REQUEST_URI} ^/public
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /public/index.php
```
