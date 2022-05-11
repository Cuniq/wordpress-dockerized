wpinstall: configure

configure:

	@echo "⚙️ Configuring Wordpress parameters..."
	wp core install \
		--url=${WORDPRESS_WEBSITE_URL_WITHOUT_HTTP}:${WORDPRESS_CUSTOM_HTTP_PORT} \
		--title="$(WORDPRESS_WEBSITE_TITLE)" \
		--admin_user=${WORDPRESS_ADMIN_USER} \
		--admin_password=${WORDPRESS_ADMIN_PASSWORD} \
		--admin_email=${WORDPRESS_ADMIN_EMAIL}

	wp option update timezone_string Europe/Athens
	wp plugin delete --all
	wp theme delete --all --force
	wp rewrite structure $(WORDPRESS_WEBSITE_POST_URL_STRUCTURE)
	wp theme install astra --activate
	wp plugin install wp-debugging --activate
	wp core update