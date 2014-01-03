## Gradlew Buildpack for Heroku

This buildpack can be used to run a gradle wrapper on Heroku.

Simply add a `Procfile` to the root of your project in order to bootstrap your app.
In this case a spring-boot app:

	---
	default_process_types:
		web: java -jar -Dport=$PORT build/libs/spring-boot.jar

