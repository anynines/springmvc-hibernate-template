###Spring Sample Application using Redis and PostgreSQL Services

To clone the application simply run:
<pre>
git clone git@github.com:anynines/springmvc-hibernate-template.git
</pre>

```cd``` into your new directory and follow the steps in the wizard to deploy the app on [anynines](http://www.anynines.com):

<pre>

##Pre-requisites

1) Install maven -> (brew: brew install maven)

## The following instructions are valid for the cf cli v6!!!

1)$> cf api https://api.de.a9s.eu

2)$> cf login
>> target: https://api.de.a9s.eu

Email> user@example.com
Password> **********
>> Authenticating... OK

3)$> mvn package
>> Maven Build Output ...

4)$> cp manifest.yml.v6 manifest.yml
5) vim manifest.yml -> adjust the manifest.yml file with our desired app name and route (replace "your_app_name")
6) create the needed services:
  $> cf create-service redis 100 redis-your_app_name
  $> cf create-service postgresql Pluto-free postgresql-your_app_name
7)$> cf push
8)$> cf app your_app_name
Open the url specified for the application in your web browser.
