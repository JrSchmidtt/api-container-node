# Instalação do docker container com maria db

REMOVE VERSÕES ANTERIORES DO DOCKER :
```
sudo apt-get remove \
    docker \
    docker-engine \
    docker.io \
    containerd runc -y
```
Atualizar sistema:
```
sudo apt update
```
## INSTALANDO DOCKER CE
Pre requisitos para instalar o docker community edition :
```
sudo apt install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common -y
```
Baixar e instalar docker ce :
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable" -y
```
```
sudo apt update
```
```
sudo apt install docker-ce docker-ce-cli containerd.io -y
```
### CRIANDO O CONTAINER DO MARIADB :
```
sudo docker run --restart always -d --name mariadb_api -p 3306:3306 \
    -e MYSQL_ROOT_PASSWORD=SUA_SENHA_FORTE mariadb
```
parando container :
```
sudo docker stop mariadb_api
```
listando containers :
```
docker container ls
```

delentando container
```
docker container rm <container_id>
```

### CRIANDO O CONTAINER DO MARIADB WSL 2 :
Entre PowerShelle digite:
```
docker context ls
```
Resultado:
```
NAME                DESCRIPTION                               DOCKER ENDPOINT                  KUBERNETES ENDPOINT   ORCHESTRATOR
default *           Current DOCKER_HOST based configuration   npipe:////./pipe/docker_engine                         swarm
```
Volte para sua configuração wsl/ubuntu e digite:
```
export DOCKER_HOST=unix:///var/run/docker.sock
```
Isso deve mostrar automaticamente sua saída completa ao digitar:
```
docker version
```

# INICIANDO PROJETO COM ESLINT
```
npx eslint --init
```
