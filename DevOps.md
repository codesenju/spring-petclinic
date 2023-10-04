### Run sonar scanner only
```bash
mvn -DskipTests verify sonar:sonar \
  -Dsonar.projectKey=petclinic \
  -Dsonar.projectName='petclinic' \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_***
```

```bash
export PROJECT_KEY=cicd-python-project
export AUTH_TOKEN=sqp_***
export SONARQUBE_URL=http://sonarqube:9000

docker run --net spring-petclinic_mynet  \
    --rm \
    -e SONAR_HOST_URL="${SONARQUBE_URL}" \
    -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=${PROJECT_KEY}" \
    -e SONAR_TOKEN="$AUTH_TOKEN" \
    -v "$(PWD):/usr/src" \
    sonarsource/sonar-scanner-cli
```