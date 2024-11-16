--------------------------------------------------------------------------------------------
--------------------------------- MSBuild.Version.Target -----------------------------------
--------------------------------------------------------------------------------------------

Thank you for using MSBuild.Version.Target! 🎯⚙️  

For the complete documentation, visit:  
https://github.com/guibranco/MSBuild.Version.Target/  

--------------------------------------------------------------------------------------------
## Overview

This NuGet package adds functionality to automatically update the `AssemblyInfo.cs` file 
and a version tracking file (`Version.txt`) during every project build (excluding RELEASE builds).  

### Key Features:
- Supports **Semantic Versioning (SemVer)**:  
  - **Major** and **Minor** versions are managed manually.  
  - **Build** version (Patch) is automatically incremented during builds.
- Automatically updates `AssemblyInfo.cs` and `Version.txt` after each build.  
- Fully compatible with CI/CD pipelines.  

--------------------------------------------------------------------------------------------
## Getting Started

1. **Version.txt** File:  
   Upon installation, a file named `Version.txt` is created in the `Properties` directory.  
   - Edit this file to set your starting version in the format:  
     ```
     Major.Minor.Build (e.g., 1.0.0)
     ```
   - **Note**: Major and Minor versions are not updated automatically.

2. **Build Configuration**:  
   - The auto-increment functionality is triggered during builds for configurations other than `Release`.  
   - To configure build settings:  
     - In Visual Studio: Use **Build > Configuration Manager**.  
     - In CI or command-line builds: Pass `/p:Configuration=<your_configuration>` (e.g., `Debug`).

3. **What Happens During a Build?**  
   - `Version.txt` is updated with the incremented Build number.  
   - `AssemblyInfo.cs` is updated with the latest version.

--------------------------------------------------------------------------------------------
## Version History

### v2
- Added a dependency on the **MSBuildTasks** NuGet package.

### v1
- Ensure **MSBuildExtensions** is installed:  
  Available at https://github.com/loresoft/msbuildtasks.

--------------------------------------------------------------------------------------------
