# Spring Boot Demo

Simply a simple spring boot demo app that shows examples of things like:

- Rest controllers
- Simple model objects as API objects.
- Autowiring Services/Beans
- Injecting yml configs into config objects
- Overwriting partial configurations per spring active profiles
- Spring JPA data setup
  - Connected to an in memory, non-persisting, H2 DB. Normally this would not be the case, and you would provide a conection string to an existing DB.
  - Auto-creating the table schemas in the DB using `spring.jpa.auto-dll: true`. Again, this would normally not the be case. You will either consume a DB that already exists and you do not manage the schema for, or, if you are the manager of the table schemas, I would use a management tool like liquibase or flyway that integrates nicely with spring boot.
- Bidirectional database object relationships
  - Stopping infinite recursions on serialization by using @JsonIgnore
- JpaRepository custom methods using natural language with no implemention needed
- Lombok @Data and @Builder annotations
- Lombok @Slf4j annotation for logging

To run the app, use `./gradlew bootRun` in the root of this directory. It will be hosted at `localhost:8081`

To run with a different spring active profile, simply append `--args='--spring.profiles.active=MyProfile'` to the above command, or set the ENV variable of `SPRING_PROFILES_ACTIVE` as a comma delimited list.

In this repo, your response at the path `/greetingService` will change if you launch with the profile `carson`.
