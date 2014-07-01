###Spring Sample Application using Redis and PostgreSQL Services

To clone the application simply run:
<pre>
git clone git@github.com:anynines/springmvc-hibernate-template.git
</pre>

```cd``` into your new directory and follow the steps in the wizard to deploy the app on [anynines](http://www.anynines.com):

##Pre-requisites

1) Install maven -> (brew: brew install maven)

## The following instructions are valid for the cf cli v6!!!

1. <pre>$> cf api https://api.de.a9s.eu</pre>

2. <pre>$> cf login</pre>
	<pre>
	target: https://api.de.a9s.eu
	Email> user@example.com
	Password> **********
	Authenticating... OK
	</pre>

3. <pre>$> mvn package</pre>
	<pre>
	Maven Build Output ...
	</pre>

4. <pre>$> cp manifest.yml.v6 manifest.yml</pre>

5. <pre> vim manifest.yml </pre>
    adjust the manifest.yml file with our desired app name and route (replace "your_app_name")

6. ##### create the needed services:
	<pre>
	  $> cf create-service redis 100 redis-your_app_name		
	  $> cf create-service postgresql Pluto-free postgresql-your_app_name
	</pre>	

7. ##### deploy your app
	<pre> $> cf push </pre>

8. ##### check your app's status
	<pre> $> cf app your_app_name </pre>

Open the url specified for the application in your web browser.
