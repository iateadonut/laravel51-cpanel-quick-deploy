## Laravel 5.1 CPanel quick-deploy

This is a repo for quickly deploying Laravel 5.1 to CPanel.

In your home directory:
	git clone

Then:
	cd laravel
	cp .env.example .env
	composer install
	chmod -R 777 storage
	php artisan key:generate

And maybe:
	chmod 777 bootstrap/cache
You'll only need to do this if you're deploying on a local instance.  CPanel should have no trouble writing to bootstrap/cache as 775.

