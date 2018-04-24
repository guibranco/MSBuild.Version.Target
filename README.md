# MSBuild.Version.Target

[![Build status](https://ci.appveyor.com/api/projects/status/bfwtumc7xs6sfh0m?svg=true)](https://ci.appveyor.com/project/guibranco/msbuild-version-target)
[![MSBuild.Version.Target NuGet Version](https://img.shields.io/nuget/v/MSBuild.Version.Target.svg)](https://www.nuget.org/packages/MSBuild.Version.Target/)
[![MSBuild.Version.Target NuGet Downloads](https://img.shields.io/nuget/dt/MSBuild.Version.Target.svg)](https://www.nuget.org/packages/MSBuild.Version.Target/)

Provides a NuGet package that adds functionality to your project to auto increment the version build before every non release configuration build. 

This package adds a Version.txt with SemVer version (you must update the major and minor version manually, only build is updated via this functionality). 

The target updates the AssemblyInfo.cs and the Version.txt of the installed project after each build that is not with the Release configuration. 

----------

NuGet package: https://www.nuget.org/packages/MSBuild.Version.Target
```ps
Install-Package MSBuild.Version.Target
```

----------

After installation, open **Properties>Version.txt** and update the file to match your current project version (SemVer like: Major.Minor.Patch, as Patch being the Build incremental).

Open the **.csproj** file of the project (via Notepad, Notepad++, VS Code, any text editor you prefer) and at the bottom of the file add the following code (NuGet dosen't allow changes in the .csproj automaticly):

```xml
<Target Name="BeforeBuild">
    //..others targets calls already in your .csproj BeforeBuild target, if any.
    <CallTarget Targets="MSBuild.Version.Target" />
</Target>
```
Be careful, check if you already have a target named "**BeforeBuild**" in your .csproj, if so, just call the target to increment, else create the Target **BeforeBuild** as the example above