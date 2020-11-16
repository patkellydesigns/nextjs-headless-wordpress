- Headless WordPress, using Decoupled Architecture in Next.js
- Backend in WordPress.
- Front end in React.

## Setup

First clone/fork the repo and cd into it.

```bash
git clone https://github.com/patkellydesigns/meganwp.git
cd meganwp
```
 
## Debugging

1. If you get 404 on frontend for graphql request, check to see that the `.htaccess` file in wordpress directory has the rules

```shell script
# BEGIN WordPress
# The directives (lines) between "BEGIN WordPress" and "END WordPress" are
# dynamically generated, and should only be modified via WordPress filters.
# Any changes to the directives between these markers will be overwritten.
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
</IfModule>

# END WordPress
```

2. If front-end is throwing some other error.

- Check if all the required WordPress plugins form `backend/plugins-collection` are active.
- Ensure you have updated the block registry from WordPress backend > GraphQL Gutenberg 
- Ensure that `.env` file has correct env variables and their values in `frontend/.env`

## References for Docker Images.

1. [phpMyAdmin](https://github.com/fuadajip/dockercompose-mysql-phpmyadmin/blob/master/docker-compose.yml)
