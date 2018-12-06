# Usage

Clone this repository, then clone your drupal repository using the commands below

```
# clone oakton-drupal
git clone git@github.com:oaktondigital/oakton-drupal oakton-drupal && cd $_
# clone your drupal repository
git clone git@github.com:<repoorg>/<reponame>.git drupal
```
You will also need to copy in the `settings.php` to `drupal/sites/default/settings.php` file, make sure your main drupal repositing has `sites/*/settings.php` in the .gitignore file
```
cp oakton.settings.php drupal/sites/default/settings.php
```

# Requirements
## Install Docker
  * [Linux](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
  * [MacOS](https://docs.docker.com/docker-for-mac/install/)

## Install Docker-Compose
  * [Docker-Compose](https://docs.docker.com/compose/install/)

## Install Ahoy
  * [Ahoy Install](https://github.com/ahoy-cli/ahoy)
  * [Ahoy Releases](https://github.com/ahoy-cli/ahoy/releases)

## Install Pygmy
  * [Pygmy](https://docs.amazee.io/local_docker_development/pygmy.html#prerequisites)

# Get Started
### Start pygmy
```
pygmy up
```
### Build and start containers
```
ahoy up
```
### Install profile
If you have no database and are starting a fresh site, you can install a profile
```
ahoy install #install govcms profile if drupal is govcms distro
## OR
ahoy install-standard #install the standard drupal profile
```
### Import database
Place the `*.sql` file into the `import` directory then run the following to start the import
```
ahoy import-db
```
### If you want to use stage-file-proxy
```
ahoy drush pm-download stage_file_proxy
ahoy drush pm-enable --yes stage_file_proxy
ahoy drush variable-set stage_file_proxy_origin "https://<domain>"
```
### Log in
```
ahoy login
```

# Notes
Once it is running, you can develop as normal in the `drupal` directory which contains your git repository.
You can commit as normal inside of that directory, but make sure you run any ahoy commands in the `oakton-drupal` directory.

If you are not developing, shutdown the development environment by running the following
## Stop Environment
```
ahoy stop
pygmy stop
```

## Destroy Environment
```
ahoy down
pygmy down
```

# Access
Once the containers are running, the following URLs will be available

* [drupal](http://drupal.local.oakton.digital)
* [phpMyAdmin](http://myadmin.local.oakton.digital:8089)
* [MailHog Mailcatcher](http://mailhog.docker.amazee.io/)
