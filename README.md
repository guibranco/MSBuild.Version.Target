# MSBuild.Version.Target

[![wakatime](https://wakatime.com/badge/github/guibranco/MSBuild.Version.Target.svg)](https://wakatime.com/badge/github/guibranco/MSBuild.Version.Target)
[![Build status](https://ci.appveyor.com/api/projects/status/bfwtumc7xs6sfh0m?svg=true)](https://ci.appveyor.com/project/guibranco/msbuild-version-target)
[![MSBuild.Version.Target NuGet Version](https://img.shields.io/nuget/v/MSBuild.Version.Target.svg)](https://www.nuget.org/packages/MSBuild.Version.Target/)
[![MSBuild.Version.Target NuGet Downloads](https://img.shields.io/nuget/dt/MSBuild.Version.Target.svg)](https://www.nuget.org/packages/MSBuild.Version.Target/)

[![Maintainability](https://api.codeclimate.com/v1/badges/42d02eaff227c10bb2b3/maintainability)](https://codeclimate.com/github/guibranco/MSBuild.Version.Target/maintainability)
[![Test Coverage](https://api.codeclimate.com/v1/badges/42d02eaff227c10bb2b3/test_coverage)](https://codeclimate.com/github/guibranco/MSBuild.Version.Target/test_coverage)
[![CodeFactor](https://www.codefactor.io/repository/github/guibranco/MSBuild.Version.Target/badge)](https://www.codefactor.io/repository/github/guibranco/MSBuild.Version.Target)

🎯⚙️ Provides a NuGet package that adds functionality to your project to auto-increment the version build before every non-release configuration build. 

This package adds a Version.txt with the SemVer version (you must manually update the major and minor versions. Only the build is updated via this functionality). 

The target updates the AssemblyInfo.cs and the Version.txt of the installed project after each build, which is not with the Release configuration. 

----------

## Installation

Nuget package: https://www.nuget.org/packages/MSBuild.Version.Target


```ps
Install-Package MSBuild.Version.Target
```


## Versioning

The version number for all projects within the solution is managed centrally using the `SolutionVersion.txt` file located at the root of the repository. Update this file to change the version across all projects.

Ensure consistency by modifying the version only in the `SolutionVersion.txt` file.
----------

## Instructions

After installation, open **Properties > Version.txt** and update the file to match your current project version (SemVer like Major.Minor.Patch, as Patch is the Build incremental).

The configuration mentioned above is passed to the MSBuild call of a project being built.
This can be set by Visual Studio in the Configuration Manager or in a manual/CI building passing the arguments */p:Configuration=Debug* (for a Debug build). Any value different from **Release** will activate this tool in the build process. 
