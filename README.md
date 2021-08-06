mvn io.quarkus:quarkus-maven-plugin:1.3.2.Final:create \
    -DprojectGroupId=org.acme \
    -DprojectArtifactId=openshift-quickstart \
    -DclassName="org.acme.rest.GreetingResource" \
    -Dpath="/greeting" \
    -Dextensions="openshift"

```yaml
quarkus.kubernetes-client.trust-certs=true
quarkus.s2i.base-jvm-image=registry.redhat.io/openjdk/openjdk-11-rhel7:1.1-14
quarkus.openshift.expose=true
```

```bash
./mvnw clean package -Dquarkus.container-image.build=true
```
```bash
./mvnw clean package -Dquarkus.kubernetes.deploy=true
```
