###Spring Sample Application using Redis and PostgreSQL Services

To clone the application simply run:
<pre>
git clone git@github.com:anynines/springmvc-hibernate-template.git
</pre>

```cd``` into your new directory and follow the steps in the wizard to deploy the app on [anynines](http://www.anynines.com):

##Pre-requisites

1. Install maven -> [Apache Maven](http://maven.apache.org/download.cgi)
2. Install the cf cli -> [CF CLI installation tutorial](https://anynines.zendesk.com/entries/60241846-How-to-install-the-CLI-v6)

#### The following instructions are valid for the cf cli v6!!!

* **Connect to the anynines api**
	<pre>$> cf api https://api.de.a9s.eu</pre>

* **Login to anynines**
	<pre>$> cf login</pre>
	<pre>
	target: https://api.de.a9s.eu
	Email> user@example.com
	Password> **********
	Authenticating... OK</pre>

* **Build the project using maven**
	<pre>$> mvn package</pre>
	<pre>Maven Build Output ...	</pre>

* **Copy over the manifest template**
	<pre>$> cp manifest.yml.v6 manifest.yml</pre>

* **Adjust the manifest.yml file with our desired app name and route (replace "your_app_name")**
	<pre> vim manifest.yml </pre>
    
* **Create the needed services**
	<pre>
	  $> cf create-service redis 100 redis-your_app_name
	  $> cf create-service postgresql Pluto-free postgresql-your_app_name
	</pre>

* **Deploy your app**
	<pre> $> cf push </pre>

* **Check your app's status**
	<pre> $> cf app your_app_name </pre>

Open the url specified for the application in your web browser.
