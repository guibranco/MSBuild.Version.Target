# MSBuild.Version.Target
Provides a NuGet package that adds functionality to your project to auto increment the version build and revision before every Debug build. This package adds a Version.txt with SemVer version (you must update the major and minor version manually, only build and revision is updated via this package/target). The target updates the AssemblyInfo.cs and the Version.txt of the installed project. This package relies that you uses a SVN like version control system (as it revision is incremental integer). It uses the Tortoise SVN for get the revision number of the folder of the .csproj
