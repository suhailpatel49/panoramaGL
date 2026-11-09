# Publishing `io.github.suhailpatel49:panoramagl`

Bump `version` and `coordinates(...)` in `library/build.gradle` before each release.
Published so far: `1.14` (from the upstream `1.14` tag), `1.14.1`.

## Required Secrets

Use a Sonatype Central Portal user token, not your login password.

```sh
export ORG_GRADLE_PROJECT_mavenCentralUsername='CENTRAL_PORTAL_TOKEN_USERNAME'
export ORG_GRADLE_PROJECT_mavenCentralPassword='CENTRAL_PORTAL_TOKEN_PASSWORD'
export ORG_GRADLE_PROJECT_signingInMemoryKey="$(gpg --armor --export-secret-keys YOUR_GPG_KEY_ID)"
export ORG_GRADLE_PROJECT_signingInMemoryKeyPassword='YOUR_GPG_KEY_PASSWORD'
```

For Vanniktech `0.36.0`, keep this set for Central Portal publishing:

```sh
export ORG_GRADLE_PROJECT_SONATYPE_HOST='CENTRAL_PORTAL'
```

## Verify Locally

```sh
./gradlew :library:publishToMavenLocal
```

## Upload To Maven Central

Manual release from the Central Portal UI:

```sh
./gradlew :library:publishToMavenCentral
```

Automatic publish and release:

```sh
./gradlew :library:publishAndReleaseToMavenCentral
```

The published dependency will be:

```gradle
implementation("io.github.suhailpatel49:panoramagl:1.14.1")
```
