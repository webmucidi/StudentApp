# 1. Build ortamı
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app
COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o out

# 2. Çalışma ortamı
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app
COPY --from=build /app/out .

# 3. Port ve başlangıç komutu
EXPOSE 80
ENTRYPOINT ["dotnet", "StudentApp.dll"]
