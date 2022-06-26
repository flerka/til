# Amazon lambda tools

```
    dotnet tool install -g Amazon.Lambda.Tools
    dotnet lambda deploy-function --function-name FUNCTION_NAME
    dotnet lambda invoke-function FUNCTION_NAME -p "Hello World"
    dotnet lambda delete-function --function-name FUNCTION_NAME
```