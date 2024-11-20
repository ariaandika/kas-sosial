# Kas Sosial

## Android Development

- development computer must connect to the same wifi with the android
- connect android with cable, then run `adb start-server`

## Horrible Gradle Version Matrix War

basically java gradle does not forward or backward compatible

[source](https://docs.gradle.org/current/userguide/compatibility.html#java)

resolve:

- download gradle-8.9-bin from gradle web
- put gradle in `~/.gradle/wrapper/dist/gradle-8.9-bin/<HASH>`
- download jdk version 21
- setup android stuff with cmdline tools

