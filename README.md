# SIMPLE SUBSCRIPTION PLATFORM
Create a simple subscription platform(only RESTful APIs with MySQL) in which users can subscribe to a website (there can be multiple websites in the system). Whenever a new post is published on a particular website, all it's subscribers shall receive an email with the post title and description in it. (no authentication of any kind is required)

## Installation Setup
1. Clone the repository
2. Run `composer install` to install the dependencies.
3. Run `composer run-script post-root-package-install` to generate your local `.env` file.
4. Run `composer run-script post-create-project-cmd` to generate your application key.
5. Open your `.env` and configure your database credentials.
6. Run `php artisan migrate --seed`

## Documentation
https://documenter.getpostman.com/view/7154640/UVC6j71T

## Queue
The post notification to subscribers are queued, so you will need to run `php artisan queue:listen`

## Bonus
There is a command to send "post-created" emails to subscribers: `php artisan notify:subscribers`.

I did not add this implementation by default since the mails will be sent upon the post creation via event/listener (observer), but if you do want to test it, simply run the command.
