-------------------------------------------------------------------------
------------------ Version Targets - Editora Inovação -------------------
-------------------------------------------------------------------------

This Nuget Package add the functionality of auto update AssemblyInfo.cs
file after every build of project.

A file named 'Version.txt' was created into the Properties directory.
Update it with the current version, in the following format: 1.0.0

On every build (non-RELEASE config) done file will be update with 
Major version, Minor version, Build (incremented, every build)

Make sure that you have installed:
- MSBuildExtensions (https://github.com/loresoft/msbuildtasks)

Import the MSBuild.Community.Tasks.Targets in your *.csproj

<Import Project="$(MSBuildExtensionsPath)\MSBuildCommunityTasks\MSBuild.Community.Tasks.Targets" />

Then just call the Version target inside your BeforeBuild target, like this:

<Target Name="BeforeBuild">
	//..others targets calls.
    <CallTarget Targets="Version" />
</Target>