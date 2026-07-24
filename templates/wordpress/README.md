# WordPress template

A barebones WordPress project running locally with DDEV.

WordPress core, bundled themes, uploads, generated configuration and the local
database are not stored in Git. Custom themes and plugins added to `wp-content`
will be included.

## Create a project

Copy this folder into `work/<project-slug>`, then set a unique DDEV project name:

```powershell
ddev config --project-name=<project-slug>
```

## Install

Run these commands once in a new copy of the template:

```powershell
ddev start
ddev exec bash -lc 'set -e; rm -rf /tmp/wordpress-core-download; mkdir /tmp/wordpress-core-download; curl -fsSL https://wordpress.org/wordpress-7.0.2.zip -o /tmp/wordpress-core-download/wordpress.zip; unzip -q /tmp/wordpress-core-download/wordpress.zip -d /tmp/wordpress-core-download; cp -a /tmp/wordpress-core-download/wordpress/. /var/www/html/; rm -rf /tmp/wordpress-core-download'
ddev restart
ddev wp core install --url='$DDEV_PRIMARY_URL' --title='<Site title>' --admin_user=admin --admin_email='<email>' --prompt=admin_password
ddev wp post delete 1 2 3 --force
ddev wp option update blog_public 0
ddev wp rewrite structure '/%postname%/'
ddev wp core verify-checksums
```

The restart generates local WordPress configuration after core has been
downloaded. Core is extracted with the container's native `unzip` because the
current WP-CLI extraction truncates some WordPress 7.0.2 filenames on Windows.
Choose a unique administration password for each project.

## Use

```powershell
ddev start
ddev launch
```

Open WordPress administration with `ddev launch /wp-admin/`.

Stop the project with `ddev stop`. Run WordPress CLI commands with `ddev wp`, and open captured development email with `ddev mailpit`.

If Windows does not yet trust DDEV's local HTTPS certificates, run `mkcert -install` in an interactive PowerShell window, approve the Windows security prompt, then run `ddev restart`.

## Core updates

Run `ddev wp core verify-checksums` after updates. When this template adopts a
new WordPress version, update the pinned version in the install command above.
