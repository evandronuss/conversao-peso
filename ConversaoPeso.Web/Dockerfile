FROM mcr.microsoft.com/dotnet/sdk:5.0 as build
WORKDIR /app
COPY . .
RUN dotnet publish -c Release -o dist

FROM mcr.microsoft.com/dotnet/aspnet:5.0 as final
WORKDIR /app
COPY --from=build /app/dist .
EXPOSE 80
ENTRYPOINT [ "dotnet", "ConversaoPeso.Web.dll" ]