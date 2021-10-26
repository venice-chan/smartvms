## steps in solution

- dotnet new webapi -o Identity.API
- dotnet new sln
- dotnet sln add src/services/identity/identity.api

## steps in individual project

- dotnet add package Microsoft.EntityFrameworkCore.SqlServer

## steps in libraries

- create nuget.config in root solution level
- copy paste content from %AppData%\NuGet\NuGet.Config
- dotnet new classlib -o AuditTrail

## steps to use github cli

- install gh cli from [https://cli.github.com/manual/]
- gh auth login
- gh config set editor "code --wait"
