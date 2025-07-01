csprojでのTask登録例
```xml
<Target Name="NSwagOpenApi" AfterTargets="Build" Condition="'$(Configuration)' == 'Debug'">
    <Exec Command="$(NSwagExe_Net80) aspnetcore2openapi /project:$(MSBuildProjectFullPath) /output:$(OutputPath)openapi.json /nobuild:true"
          WorkingDirectory="$(ProjectDir)"
          EnvironmentVariables="ASPNETCORE_ENVIRONMENT=Development" />
  </Target>
```
