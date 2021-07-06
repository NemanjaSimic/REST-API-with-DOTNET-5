# REST-API-with-DOTNET-5

Simple project in .NET 5 for learning new stuff in my spare time.
Following Julio Casal.

How to run with kubernetes:

1. cd .\kubernetes\
2. kubectl apply -f .\catalog.yaml
3. kubectl apply -f .\mongodb.yaml
   (kubectl get pods - to see if the pods are live and ready)

How to run with Docker:
1)docker network create net5tutorial

2)docker run -d --rm --name mongo -p 27017:27017 -v mongodbdata:/data/db mongo -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=Pass#word1 --network=net5tutorial mongo

3)docker run -it --rm -p 8080:80 -e MongoDbSettings:Host=mongo -e MongoDbSettings:Password=Pass#word1 --network=net5tutorial simicnemanja/catalog:v3

Creating image from code:
docker build -t [name]:[version] .

Secrets management with user-secrects (development only):
dotnet user-secrets init (download the package)
dotnet user-secrets set MongoDbSettings:Password Pass#word1 (set variable)

Package for health check of dependend services:
dotnet add package AspNetCore.HealthChecks.MongoDb
