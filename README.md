# cloudrun-dotnet

dotnet publish -c Release

docker build -t cloudrun-dotnet .
docker run --publish 8080:8080 cloudrun-dotnet

docker tag cloudrun-dotnet gcr.io/nugraha-51412/cloudrun-dotnet
docker push gcr.io/nugraha-51412/cloudrun-dotnet

gcloud run deploy --image gcr.io/nugraha-51412/cloudrun-dotnet --platform managed

gcloud run deploy cloudrun-dotnet --image gcr.io/nugraha-51412/cloudrun-dotnet --platform managed --region=us-central1 --allow-unauthenticated
