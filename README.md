# Applying an init script to a project with buildSrc

## Observed behavior

### Providing an init script in Gradle user home

Copying the init script `init.gradle` to the `<Gradle user home>/init.d` correctly applies the repository Maven Central to all projects of the build including `buildSrc`.

    ./gradlew tasks

### Providing an init script from the command line

Using the command line option `-I` instead does not show the same behavior. It seems like the logic of the initialization script does not apply to the `buildSrc` project. As a result, the build fails.

    ./gradlew tasks -I init.gradle