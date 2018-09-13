# Root

This Gradle project contains two subprojects: `server-one` and `server-two`.

## Scenario: different Gradle Wrapper versions

The projects each have the following Gradle Wrapper versions:

- `root`: Gradle Wrapper 4.10
- `server-one`: Gradle Wrapper 2.0
- `server-two`: Gradle Wrapper 4.5

Try calling the following commands:

- `./gradlew info`
- `server-one/gradlew info`
- `server-two/gradlew info`

Notice how only `server-one/gradlew info` doesn't print out warnings about `server-one`'s deprecated task notation, as it's the only one where that notation wasn't deprecated.

Depending on which wrapper you use to call `gradle info`, or `gradle :<project>:info`, these will behave differently.
The wrapper you call will interpret the *entire* multi-project's build scripts.

This is probably what's causing you a lot of issues and odd behaviour. I'd recommend you consolidate on a single version, and keep a single wrapper in the root project.

## Tasks

### info

All projects have an `info` task, which prints their project name, the Gradle version they were called with and whether or not they are using a deprecated task notation.
