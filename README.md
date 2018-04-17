# wordpress-git

This is a simple skeleton repo for managing a WordPress site using: **wp-cli**, **git**, **composer**
![Wordpress + Git + Composer](https://cdn.deliciousbrains.com/content/uploads/2015/05/Git-Composer.png)

## Getting Started

1. Clone this repo within the local web root folder (eg through [GitHub Desktop](https://desktop.github.com/)/[Atom.io](https://atom.io/) and [MAMP](https://www.mamp.info/)).
2. **NB** Rename the cloned folder (_wordpress-git_) to something more friendly (eg _site-name_).
3. Within this folder, now you can alternately run:
      1. `wp core download` to install wordpress (or even better [`wp core install`](#pro-tip---creating-a-new-db-in-mamp--install-a-new-wordpress-instance))<br>`composer install` to install any required plugin/theme (`composer update` it's also fine).
      2. [`one-click-install.sh`](./one-click-install.sh) to perform all these things (and more) automatically.
6. Happy coding...

### remember to...
- Add to the **composer.json** file all of the wordpress plugins and themes (eg from [wpackagist](http://wpackagist.org/)) that might be required in this wordpress installation.
- Add to the **.gitignore** file all of your custom plugins/themes that you want to keep under git control (add `!wp-content/plugins/my-plugin-name` for a custom plugin and `!wp-content/themes/my-theme-name` for a custom theme).

### Requirements
**[localhost](http://127.0.0.1):** [wp-cli](https://make.wordpress.org/cli/handbook/installing/), [git](https://git-scm.com/downloads), [composer](https://getcomposer.org/doc/00-intro.md) (and wordpress..)

**live server:** ftp access or _**even better**_ [GitHubUpdater CI](https://medium.com/@limikael/continuous-integration-for-wordpress-d152ec4852e5) (and wordpress..)

## Contribution

 You can fork it and submit your change with a pull request !
 
---

#### Pro Tip - "Creating a new DB in MAMP & Install a new Wordpress instance":

`wp core download `**`--locale=it_IT`**

`wp core config `**`--dbname=wp_test`**` --dbuser=root --dbpass=root --dbhost=127.0.0.1`

`wp db create`

`wp core install `**`--url=http://127.0.0.1/folder-name`**` `**`--title="Site Name"`**` `**`--admin_name="admin"`**` `**`--admin_password="admin"`**` --admin_email="example@example.com" --skip-email`

#### Pro Tip - "Force using MAMP's bundled binaries in a Linux/Mac OS"
1. run: `nano ~.bash_aliases`
2. append the following lines:
   - ``PHP_VERSION=`ls /Applications/MAMP/bin/php/ | sort -n | tail -1` ``
   - ``export PATH=/Applications/MAMP/bin/php/${PHP_VERSION}/bin:$PATH ``
   - ``alias mysql='/Applications/MAMP/Library/bin/mysql' ``
3. run: `source ~.bash_aliases`

#### Pro Tip - "Force using Windows binaries in a Windows Subsystem for Linux ("Windows Bash")"
1. run `nano ~.bash_aliases`
2. append the following lines:
   - `alias php=php.exe`
   - `alias wp='cmd.exe /c wp'`
   - `alias composer='cmd.exe /c composer'`
3. run `source ~.bash_aliases`
4. (optional) create a shortcut to your windows user folder: `ln -s /mnt/c/Users/<USERNAME> ~/<USERNAME>`
