# REST-API-with-DOTNET-5

Simple project in .NET 5 for learning new stuff in my spare time.
Following Julio Casal.

MongoDB connection settings:
Host : localhost
Port : 27018

For easily setting MongoDb, you can use mongo docker image:
docker run -d --rm --name mongo -p 27018:27017 -v mongodbdata:/data/db mongo

Setting MongoDB with auth:
docker run -d --rm --name mongo -p 27018:27017 -v mongodbdata:/data/db mongo -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=Pass#word1 mongo

Secrets management with user-secrects:

dotnet user-secrets init (download the package)
dotnet user-secrets set MongoDbSettings:Password Pass#word1 (set variable)

Package for health check of dependend services:
dotnet add package AspNetCore.HealthChecks.MongoDb
