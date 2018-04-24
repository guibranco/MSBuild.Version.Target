# MSBuild.Version.Target
Provides a NuGet package that adds functionality to your project to auto increment the version build before every non release configuration build. 
This package adds a Version.txt with SemVer version (you must update the major and minor version manually, only build is updated via this functionality). 
The target updates the AssemblyInfo.cs and the Version.txt of the installed project after each build that is not with the Release configuration. 

To install add the package via NuGet

Via graphic interface: MSBuild.Version.Target
Via command-line: Install-Package -id MSBuild.Version.Target

After installation, open Properties > Version.txt and update the file to match your current project version (SemVer like: Major.Minor.Patch, as Patch being the Build incremetal)
Open the .csproj file of the project (via Notepad, Notepad++, VS Code, any text editor you prefer) and at the bottom of the file add the following code (NuGet dosen't allow change the .csproj automatic):


<Import Project="$(MSBuildExtensionsPath)\MSBuildCommunityTasks\MSBuild.Community.Tasks.Targets" />
<Target Name="BeforeBuild">
	//..others targets calls.
    <CallTarget Targets="Version" />
</Target>

Be careful, check if you already have a target named "BeforeBuild" in your .csproj, if so, just call the target to increment, else create the Target BeforeBuild as the example above