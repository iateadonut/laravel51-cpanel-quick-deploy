## Laravel 5.1 CPanel quick-deploy

This is a repo for quickly deploying Laravel 5.1 to CPanel.  These instructions will make it easier when you deploy this application to your localhost and to the live instance (assuming you're setting up a staging environment now).

In your home directory:

	wget https://github.com/iateadonut/laravel51-cpanel-quick-deploy/archive/master.zip
	
	unzip master.zip
	
	rmdir public_html
	
	mv laravel51-cpanel-quick-deploy-master/* ./
	
	mv laravel51-cpanel-quick-deploy-master/.git* ./
	
Clean up the installation files:

	rmdir laravel51-cpanel-quick-deploy-master/
	
	rm master.zip

Then:

	cd laravel
	
	cp .env.example .env
	
	composer install
	
	chmod -R 777 storage
	
	php artisan key:generate
	

And maybe:

	chmod 777 bootstrap/cache
	
You'll only need to do this if you're deploying on a local instance.  CPanel should have no trouble writing to bootstrap/cache as 775.

Now create your git repo:

	cd ~
	
	rm readme.md

	git init
	
	git config user.email "email@my.com"
	
	git config color.ui true
	
	git add -A
	
	git commit -m "Initial Commit"
	
Deploying on your local computer should now be easy:

	git clone user@server:~ appname
	
	cd appname
	
Then start again on your local computer with the instructions above starting where it says "Then:"
