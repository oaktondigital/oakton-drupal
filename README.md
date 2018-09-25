# Usage

Clone this repository, then clone your drupal repository using the commands below

```
git clone git@github.com:oaktondigital/oakton-drupal oakton-drupal && cd $_
GIT_REPO=git@github.com:<repoorg>/<reponame>.git
git clone ${GIT_REPO} drupal
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
### Import database
Place the `*.sql` file into the `import` directory
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

# Access
Once the containers are running, the following will be available

* [drupal](http://drupal.local.oakton.digital)
* [phpMyAdmin](http://myadmin.local.oakton.digital:8089)
