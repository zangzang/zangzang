### Hi there 👋

dotnet build WebApplication1.csproj /p:DeployOnBuild=true /p:PublishProfile=FolderProfile
dotnet build /p:DeployOnBuild=true /p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
dotnet build /p:DeployOnBuild=true /p:PublishProfile=FolderProfile
dotnet publish /p:Configuration=Release /p:PublishProfile=FolderProfile

dotnet publish -c Release -o D:\ws\wwwroot
dotnet publish -c Release /p:PublishDir=D:\ws\wwwroot

-- not tested --

Framework Dependent Publish

Normal publish
dotnet publish

Single-file publish
dotnet publish -r win-x64 --self-contained=false /p:PublishSingleFile=true -o D:\ws\wwwroot
dotnet publish -r win-x64 --self-contained=true /p:PublishSingleFile=true -o D:\ws\wwwroot

Self-Contained Publish
dotnet publish -r win-x64

Single-file publish Linux:
dotnet publish -r linux-x64 /p:PublishSingleFile=true

Single-file publish Windows:
dotnet publish -r win-x64 /p:PublishSingleFile=true

Single-file publish Windows with Extraction
dotnet publish -r win-x64 /p:PublishSingleFile=true /p:IncludeNativeLibrariesForSelfExtract=true
