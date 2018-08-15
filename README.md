# MSBuild.Version.Target

[![Build status](https://ci.appveyor.com/api/projects/status/bfwtumc7xs6sfh0m?svg=true)](https://ci.appveyor.com/project/guibranco/msbuild-version-target)
[![MSBuild.Version.Target NuGet Version](https://img.shields.io/nuget/v/MSBuild.Version.Target.svg)](https://www.nuget.org/packages/MSBuild.Version.Target/)
[![MSBuild.Version.Target NuGet Downloads](https://img.shields.io/nuget/dt/MSBuild.Version.Target.svg)](https://www.nuget.org/packages/MSBuild.Version.Target/)

Provides a NuGet package that adds functionality to your project to auto increment the version build before every non release configuration build. 

This package adds a Version.txt with SemVer version (you must update the major and minor version manually, only build is updated via this functionality). 

The target updates the AssemblyInfo.cs and the Version.txt of the installed project after each build that is not with the Release configuration. 

----------

Nuget package: https://www.nuget.org/packages/MSBuild.Version.Target


```ps
Install-Package MSBuild.Version.Target
```

----------

After installation, open **Properties > Version.txt** and update the file to match your current project version (SemVer like: Major.Minor.Patch, as Patch being the Build incremental).

----------

The configuration mentionend above is the configuration passed to the MSBuild call of a project being built.
This can be set by the Visual Studio in the *Configuration Manager* or in a manual/CI building passing the arguments */p:Configuration=Debug* (for a Debug build). This mean that any value different from **Release** will activate this tool in the build process. 
