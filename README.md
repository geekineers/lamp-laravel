# geekineers/lamp-laravel
---

Docker image with LAMP and Laravel installed

Mount your Laravel project host directory to `/var/www/app`:

```
docker run -d --name=my-dev-container -v <project directory on host machine>:/var/www/app -P -t -i geekineers/lamp-laravel:dev
```

Then you can attach to your newly made container:

```
docker exec -ti my-dev-container /bin/bash
```

and run `composer install` at app directory to initialize Laravel project:

```
cd /var/www/app
composer install
```

**IMPORTANT:** This will not work with OSX due to limitations in boot2docker's way of handling OSX and Windows filesystems. You'll be running into file permission errors. Alternatively, we have an OSX flavor of the image: [geekineers/osx-lamp-laravel](https://)
