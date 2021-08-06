mvn io.quarkus:quarkus-maven-plugin:1.3.2.Final:create \
    -DprojectGroupId=org.acme \
    -DprojectArtifactId=openshift-quickstart \
    -DclassName="org.acme.rest.GreetingResource" \
    -Dpath="/greeting" \
    -Dextensions="openshift"

./mvnw clean package -Dquarkus.container-image.build=true
./mvnw clean package -Dquarkus.kubernetes.deploy=true
