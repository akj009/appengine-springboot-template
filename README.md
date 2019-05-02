SpringBoot Archetype Template for App Engine Standard (Java 8)
============================

This generates an archetype in your local m2 catalog which contains the project structure and all the required dependencies required for creating a Spring Boot Micro-Service on Google App Engine Standard.

See the [Google App Engine standard environment documentation][ae-docs] for more
detailed instructions.

[ae-docs]: https://cloud.google.com/appengine/docs/java/

* [Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Maven](https://maven.apache.org/download.cgi) (at least 3.5)
* [Google Cloud SDK](https://cloud.google.com/sdk/) (aka gcloud command line tool)
* [Spring Boot](https://spring.io/projects/spring-boot)

## Setup

* Download and initialize the [Cloud SDK](https://cloud.google.com/sdk/)

    `gcloud init`

* Create an App Engine app within the current Google Cloud Project

    `gcloud app create`

## Maven
### Creating the Service

 1. Clone this repository on your local.
 2. Run the following command to generate archetype for your local maven catalog
    
    `mvn archetype:create-from-project`
 3. `cd` into `./target/generated-sources/archetype` and run the following to install it on your local maven catalog
 
    `mvn install`
    
 4. `cd` into a new project directory
 5. Run `mvn archetype:generate -DarchetypeCatalog=local` to create a project from this template.
 6. Configure various variables as prompted and you are good to go!

### Running locally


`mvn appengine:run`

To use vist: http://localhost:8080/

### Deploying

`mvn appengine:deploy`

To use vist:  https://YOUR-PROJECT-ID.appspot.com (in case of default service)

## Testing

`mvn verify`

As you add / modify the source code (`src/main/java/...`) it's very useful to add [unit testing](https://cloud.google.com/appengine/docs/java/tools/localunittesting)
to (`src/main/test/...`).  The following resources are quite useful:

* [Junit4](http://junit.org/junit4/)
* [Mockito](http://mockito.org/)
* [Truth](http://google.github.io/truth/)


For further information, consult the
[Java App Engine](https://developers.google.com/appengine/docs/java/overview) documentation.
