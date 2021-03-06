# Unflare - Untorch clone

Untorch referral tool open-source clone based on Laravel (PHP) & Bootstrap3.  

- **Demo** on : <http://unflare.yebsoft.com>
- Screenshots: [Landing Page](https://github.com/younes0/unflare/blob/master/data/docs/unflare-step1.png), [Form submitted](https://github.com/younes0/unflare/blob/master/data/docs/unflare-step2.png)

## Non-technical?

Use [Kickofflab](http://kickofflabs.com/): <https://www.youtube.com/watch?t=160&v=QnPb8UvVC5o>

## Requirements

- a [Dedicated Server](http://www.kimsufi.com/us/en/) or a [VPS hosting](https://www.digitalocean.com/pricing/) or anything that allows you to setup the required services (Nginx, PHP, PostgreSQL, Memcached, Node.js).
- a [Mandrill account](Mandrillapp.com) (free up to 12 000 emails per month) to send & track emails

## Setup

- Setup Nginx and use configuration templates located in data/nginx

- Edit constants defined in the following files:
```shell
# postgresql, google analytics params etc.
config\constants.development.php
config\constants.production.php
# marketing params
config\unflr.php 
```

- Dependencies
```shell
php unflr\application\config\composer install
cd unflr\assets\grunt\ 
npm install -g grunt && npm install && grunt
```

- Create new database and execute table creations with `data\unflr_schema.sql`

- Additionally, setup queue: change the queue driver to `database` and run the queue listener: <http://laravel.com/docs/4.2/queues#running-the-queue-listener>

- Troubleshoots? Please refer to <http://laravel.com/docs/4.2/installation>

## Personalize Views

All pages & emails views are stored in `unflr\application\` and use the Blade templating system and Gettext. You can change the copywriting in .blade files directly or by editing PO files stored in `lang`. 

According to Springsheld explanations video, it is advised to keep the same layout structure and copywriting length.

## Other

- Logo by logoinstant: http://www.logoinstant.com/modern-flow-logo/
- TODO:
	* make facebook sharing optional
	* decouple from Memcached
