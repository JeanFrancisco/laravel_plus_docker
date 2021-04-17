# Laravel virtualization enviroment on Docker :whale:
Packing docker containers using official **Nginx** + **MySQL** + **PHP-FPM** images from the _Docker Hub_ to build a Laravel virtualization enviroment.

* Set your enviroment variables in `/docker/.env` and `/code/.env` for your docker services and Laravel app.

* Run:  1st.`# docker-compose build app` comand and. Then 2nd.`# docker-compose up -d` in the `/docker` folder

* After, Execute: `# docker-compose exec app composer install` to install the packages dependencies for your Laravel app with Composer.

### :tada: It's ready to watch :eye: :eye:, on your localhost. :globe_with_meridians:

>That's all for now. I will updating this in the futher... See you soon!
