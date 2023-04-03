--------------------------------------------------------------------------------------------
--------------------------------- MSBuild.Version.Target -----------------------------------
--------------------------------------------------------------------------------------------

See the full readme.MD at:

https://github.com/guibranco/MSBuild.Version.Target/blob/main/README.md

This Nuget Package add the functionality of auto update AssemblyInfo.cs file after every 
build of project.

A file named 'Version.txt' was created into the Properties directory.
Update it with the current version, in the following format: 1.0.0

On every build (non-RELEASE config) done, file Version.txt and AssemblyInfo.cs will be
updated with Major version, Minor version, Build (incremented, every build)

V2
- Dependency in MSBuildTasks nuget package

V1
Make sure that you have installed:
- MSBuildExtensions (available at https://github.com/loresoft/msbuildtasks)
