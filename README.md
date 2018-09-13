# Root

This Gradle project contains two subprojects: `server-one` and `server-two`.

## Scenario: different Gradle Wrapper versions

This is a post-cleanup multi-project Gradle setup.

The projects have been consolidated on Gradle version 4.10. Only the `root` project has a Wrapper.

## Tasks

### info

All projects have an `info` task, which prints their project name, the Gradle version they were called with and whether or not they are using a deprecated task notation.
