# corretto-8-yum

This is a clone of Dockerfile for [Corretto 8](https://aws.amazon.com/corretto/) with `yum update` applied.

## Building

```
docker build -t amazon-corretto-8-yum github.com/1zha0/docker-corretto-8-yum
```

## Testing

Tests are defined in `test-image.yaml` using [GoogleContainerTools/container-structure-test](
https://github.com/GoogleContainerTools/container-structure-test). To run tests, execute `./test-image.sh`. 

## Usage

A `JAVA_HOME` environment variable is configured to assist in tasks that require a known location of additional JRE/JDK files. For example installing a custom certificate into the default cacerts truststore.

```dockerfile
keytool -import -trustcacerts -alias myAlias -file myCert.cer -keystore $JAVA_HOME/jre/lib/security/cacerts -storepass changeit -noprompt
```