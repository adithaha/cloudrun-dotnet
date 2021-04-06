# cloudrun-dotnet

Build dotnet project
```
dotnet publish -c Release
```

Build docker image and run a test
```
docker build -t cloudrun-dotnet .
docker run --publish 8080:8080 cloudrun-dotnet
```

Push image to Google Cloud Registry
```
docker tag cloudrun-dotnet gcr.io/nugraha-51412/cloudrun-dotnet
docker push gcr.io/nugraha-51412/cloudrun-dotnet
```

Deploy into Cloud Run
```
gcloud run deploy cloudrun-dotnet --image gcr.io/nugraha-51412/cloudrun-dotnet --platform managed --region=us-central1 --allow-unauthenticated
```
