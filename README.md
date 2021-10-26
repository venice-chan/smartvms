## steps in solution

- dotnet new webapi -o Identity.API
- dotnet new sln
- dotnet sln add src/services/identity/identity.api

## steps in individual project

- dotnet add package Microsoft.EntityFrameworkCore.SqlServer

## steps in libraries

- create nuget.config in root solution level
- copy paste content from %AppData%\NuGet\NuGet.Config
- go to github > developer setting > personal access token to generate api key
- add in nuget.config
  ```
  <packageSources>
    <add key="github" value="https://nuget.pkg.github.com/venice-chan/index.json" />
  </packageSources>
  <packageSourceCredentials>
    <github>
        <add key="Username" value="venice-chan" />
        <add key="ClearTextPassword" value="<the api key>" />
    </github>
  </packageSourceCredentials>
  ```
- dotnet new classlib -o AuditTrail
- dotnet pack --configuration Release
- dotnet nuget push "bin/Release\SmartVms.AuditTrail.1.0.0.nupkg" --source "github"
- dotnet nuget push "bin/Release\SmartVms.AuditTrail.1.0.0.nupkg" --source "github" --api-key "<the api key>" to eliminate hardcode the api key in nuget config

## steps to use github cli

- install gh cli from [https://cli.github.com/manual/]
- gh auth login
- gh config set editor "code --wait"

## steps to push to github

- create repo in github, default branch as main
- git init -b main
- git add .
- git commit -m "first commit"
- git remote add origin https://github.com/venice-chan/smartvms.git
- git remote -v
- git pull --set-upstream origin main
- git pull --allow-unrelated-histories
- git push origin main
