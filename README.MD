
## DockerCompose
```
# Execute the compose file
docker-compose up -d 

# Make sure SonarQube is up
docker-compose logs --follow
```

# Optional instalation
## SonarQube
```
# Download do container docker
docker pull sonarqube:9.7.1-community

# Limpar volumes
docker system prune
```

```
# Rodar container
docker run -d --name sonarqube -e SONAR_ES_BOOTSTRAP_CHECKS_DISABLE=true -p 9000:9000 sonarqube:9.7.1-community
```

## Sonar-Scanner
```
cd tmp
sudo wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.7.0.2747-linux.zip

unzip sonar-scanner-cli-4.7.0.2747-linux.zip

mv sonar-scanner-cli-4.7.0.2747-linux /opt/sonar-scanner

vi /opt/sonar-scanner/conf/sonar-scanner.properties

# uncomment
sonar.host.url=http://localhost:9000

# Definir PATH permanente
vim ~/.bashrc
vim ~/.zshrc

# Ecreva na ultima linha
export PATH="/opt/sonarscanner/bin:$PATH"

# Carregar PATH
source ~/.zshrc
source ~/.bashrc
```
