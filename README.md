## Gradlew Buildpack for Heroku

This buildpack can be used to run a gradle wrapper on Heroku.

###Procfile

Simply add a `Procfile` to the root of your project in order to bootstrap your app.
In this case a spring-boot app:

	---
	default_process_types:
		web: java -jar -Dport=$PORT build/libs/spring-boot.jar


###Default Tasks

The gradle wrapper will be run without any tasks in order to make the build as flexible as possible. Ensure that the `build.gradle` defines a defaultTasks list including all tasks that need to be run for a successful deploy. For example, a Ratpack application would require the follwing in the build file:

	defaultTasks = ["clean", "build", "installApp"]

