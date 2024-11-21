# Kas Sosial

Bring the ergonomics of svelte and rust into the awful world of java, gradle, gradlew
with its version matrix

## Development Prerequisites

[guide from tauri](https://tauri.app/start/prerequisites/)

## Building for release

```bash
npm run tauri build # linux
npm run tauri android build # android
```

[source](https://tauri.app/distribute/)

## Android Development

- development computer must connect to the same network with the android
- connect android with cable, then run `adb start-server` from android platform-tools

## Horrible Gradle Version Matrix War

basically java gradle does not forward or backward compatible

[source](https://docs.gradle.org/current/userguide/compatibility.html#java)

when gradle not found, android tools will attempt to downloads from server, but the
target server is horrible, its very slow, download progress will get timed out by itself
before packet even reach 60%

when that happens, cancel immediately, then look for HASH in
`~/.gradle/wrapper/dist/gradle-<VERSION>-bin/<HASH>`, note the version, then download
the matching version from gradle proper website.

resolving, following version is a working example,
match gradle version with previous step and java version matrix:

- download gradle-8.9-bin from gradle website
- put downloaded file in `~/.gradle/wrapper/dist/gradle-8.9-bin/<HASH>`
- download jdk version 21
- setup android stuff with cmdline tools

## Android Signing

when it build for release, installation may yield error with the
worlds most unhelpful message ever

```
App not installed as package appears to be invalid
```

[basically application requires signing](https://github.com/tauri-apps/tauri/discussions/9872)

[here is guide from tauri](https://tauri.app/distribute/sign/android/)

