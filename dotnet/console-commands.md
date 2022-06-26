## Create dotnet solution with project
```csharp
    // create project
    dotnet new console -n PROJECT_NAME

    // create solution
    dotnet new sln --name SOLUTION_NAME

    // add project to solution
    dotnet sln add PROJECT_FOLDER/PROJECT_NAME.csproj
```

## Add package to project
```csharp
    dotnet add .\PROJECT_FOLDER\PROJECT_NAME.csproj package PACKAGE_NAME
```

## Publish to specific folder
```csharp
    dotnet publish -c Release -o=app
```