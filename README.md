# tackle-keycloak-theme
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fkonveyor%2Ftackle-keycloak-theme.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fkonveyor%2Ftackle-keycloak-theme?ref=badge_shield)


Keycloak theme for the Tackle project

## Development

Setup your dev environment executing:

```shell
./setup-dev-env.sh
```

The script above will download Keycloak and configure files. Now you can init Keycloak:

```shell
./workspace/keycloak-12.0.3/bin/standalone.sh
```

- Open your browser using http://localhost:8080/auth and create your admin user.
- Select the new theme in the Keycloak console

## Release

1. build JAR locally running:
```shell
mvn clean install
```
2. create the container image executing:
```shell
podman build -t tackle-keycloak-init:$(mvn org.apache.maven.plugins:maven-help-plugin:3.2.0:evaluate -Dexpression=project.version -q -DforceStdout) -f Dockerfile.init .
```


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fkonveyor%2Ftackle-keycloak-theme.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fkonveyor%2Ftackle-keycloak-theme?ref=badge_large)