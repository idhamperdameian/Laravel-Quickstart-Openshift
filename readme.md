# Quickstart for Laravel 5.2 PHP Framework on Openshift

[![Build Status](https://travis-ci.org/laravel/framework.svg)](https://travis-ci.org/laravel/framework)
[![Total Downloads](https://poser.pugx.org/laravel/framework/d/total.svg)](https://packagist.org/packages/laravel/framework)
[![Latest Stable Version](https://poser.pugx.org/laravel/framework/v/stable.svg)](https://packagist.org/packages/laravel/framework)
[![Latest Unstable Version](https://poser.pugx.org/laravel/framework/v/unstable.svg)](https://packagist.org/packages/laravel/framework)
[![License](https://poser.pugx.org/laravel/framework/license.svg)](https://packagist.org/packages/laravel/framework)

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable, creative experience to be truly fulfilling. Laravel attempts to take the pain out of development by easing common tasks used in the majority of web projects, such as authentication, routing, sessions, queueing, and caching.

Laravel is accessible, yet powerful, providing tools needed for large, robust applications. A superb inversion of control container, expressive migration system, and tightly integrated unit testing support give you the tools you need to build any application with which you are tasked.

## Setting up Laravel 5.2 for Openshift

This documentation is forking from [Djordje Kovacevic](https://djordjekovacevic.com/articles/run-laravel-5.1-on-openshift) website with added extra information.

### OpenShift application creation steps

- Go to OpenShift's create application page: https://openshift.redhat.com/app/console/application_types.
- Scroll to the bottom and find in the left corner "Code Anything" title with input field bellow.
- Paste URL of nginx cartridge http://cartreflect-claytondev.rhcloud.com/github/boekkooi/openshift-cartridge-nginx, then hit next button.
- Populate **Public URL** field.
- Chose **Scaling** if you want.
- Hit "Create Application" button and wait for OpenShift to build your environment.
- Continue to **the application overview page**.

### Add PHP cartridge to your application

- Find on the bottom of **the application overview page**, "see the entire list of cartridges you can add" link and click on it.
- Scroll to the bottom of the page and find "Install your own cartridge" title with input field bellow.
- Paste URL for PHP cartridge http://cartreflect-claytondev.rhcloud.com/github/boekkooi/openshift-cartridge-php, then hit next button.
- On next page check details and hit "Add Cartridge" button and wait for OpenShift to update your environment.

### Additional cartridges

If you need anything else like DB for example use existing OpenShift cartridges (MySQL, PostgreSQL).

### Prepare for Laravel 5.2

- Open terminal application.
- Clone [this application repository](https://github.com/idhamperdameian/Laravel-Quickstart-Openshift) localy
- Go to repo's root
- In OpenShift application preview page, copy git **source code** url repository
- Assuming we need to add remote url with name `openshift`, so type `git remote add openshift repo_url`. Replace **repo_url** with openshift git **source code** url repository.
- Type `git pull openshift master`.
- Remove file `public/index.html` if exist.
- Fix conflict of `.openshift/nginx.conf.erb` file, (or to make sure replace file with [nginx.conf.erb](.openshift/nginx.conf.erb)) then run "git commit".
- Push to OpenShift, type `git push openshift master`
- Your application is ready. Congratulation!.

## Official Documentation

Documentation for the framework can be found on the [Laravel website](http://laravel.com/docs).

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](http://laravel.com/docs/contributions).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell at taylor@laravel.com. All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).
