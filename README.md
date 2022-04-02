# rotten-potatoes

## Configuração

MONGODB_DB => Nome do database

MONGODB_HOST => Host do MongoDB

MONGODB_PORT => Posta de acesso ao MongoDB

MONGODB_USERNAME => Usuário do MongoDB

MONGODB_PASSWORD => Senha do MongoDB


## Criar imagem Docker e subir imagem no docker hub
```sh
cd src
docker build -t jaquelaurenti/rotten-potatoes:v1 .
docker tag jaquelaurenti/rotten-potatoes:v1 jaquelaurenti/rotten-potatoes:latest
docker login
docker push jaquelaurenti/rotten-potatoes:v1
docker push jaquelaurenti/rotten-potatoes:latest
```

## Iniciar o k3d e executar o Deployment
```sh
k3d cluster create meucluster -p "8080:30000@loadbalancer"
cd k8s
kubectl apply -f deployment.yaml
```
