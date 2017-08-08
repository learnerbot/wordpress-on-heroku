# WordPress on Heroku

## Overview

This is a simple example to understand the basics of **WordPress** powered by **Heroku**.

## Dependencies

### Runtime dependencies

The following libraries are used in the application.

*[WordPress](https://wordpress.com/)*: WordPress is an online, open source website creation tool written in PHP.

*[Heroku](https://www.heroku.com/)*: Heroku is a cloud platform that lets you build, deliver, monitor and scale apps.

*[vlucas/phpdotenv](https://github.com/vlucas/phpdotenv)*: Loads environment variables from `.env` to `getenv()`, `$_ENV` and `$_SERVER` automagically.

### Dev dependencies

The following libraries are used for the development of this project.

*[composer](https://getcomposer.org/)*: Dependency Manager for PHP.

## How to...

### Configure

The important variables from `wp/wp-config.php` were moved to environment variables. You can either specify these with the help of a `wp/.env` file or via environment vriables. There's a sample `wp/.env.sample` file to give a complete list of the variables.

The `wp-content` directory was moved outside from the core WordPress installation. This is handled in the `wp-config.php` file. If there's no `wp/wp-content/theme/` directory then it will fall back to the original `wp/site/wp-content` directory located in the WordPress core installation.

### Build and deploy app to Heroku

[Heroku CLI tool](https://devcenter.heroku.com/articles/heroku-cli) can help you build and deploy the app.

First you need to login with your Heroku credentials.

```
heroku login
```

Then you can create project in Heroku.

```
heroku create
```

This command will create a project in Heroku with some random name and create a remote git repository to which you can push the code thus deploying the app.

Push to Heroku remote repository.

```
git push heroku master
```

The contents of the `wp` directory will be deployed to an [NGINX](https://www.nginx.com/) server with the help of the `Procfile`.

### Heroku Add-ons

`TODO`
