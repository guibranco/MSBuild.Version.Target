# MSBuild.Version.Target

[![Wakatime](https://wakatime.com/badge/github/guibranco/MSBuild.Version.Target.svg)](https://wakatime.com/badge/github/guibranco/MSBuild.Version.Target)
[![Build Status](https://ci.appveyor.com/api/projects/status/bfwtumc7xs6sfh0m?svg=true)](https://ci.appveyor.com/project/guibranco/msbuild-version-target)
[![NuGet Version](https://img.shields.io/nuget/v/MSBuild.Version.Target.svg)](https://www.nuget.org/packages/MSBuild.Version.Target/)
[![NuGet Downloads](https://img.shields.io/nuget/dt/MSBuild.Version.Target.svg)](https://www.nuget.org/packages/MSBuild.Version.Target/)
[![CodeFactor](https://www.codefactor.io/repository/github/guibranco/MSBuild.Version.Target/badge)](https://www.codefactor.io/repository/github/guibranco/MSBuild.Version.Target)

🎯⚙️ **MSBuild.Version.Target** is a NuGet package that automates versioning by auto-incrementing the build version for non-release configuration builds.  

It integrates seamlessly with your project by:
- Generating and maintaining a `Version.txt` file for versioning in **Semantic Versioning (SemVer)** format.
- Automatically updating `AssemblyInfo.cs` and `Version.txt` with the incremented version during each build (except for the `Release` configuration).  

---

## 🚀 Features
- **Semantic Versioning (SemVer)** support:
  - Major and minor versions are manually maintained.
  - Build (patch) version is automatically incremented during the build process.
- Configurable via MSBuild.
- Works in CI/CD pipelines or local builds.
  
---

## 📦 Installation

To install the NuGet package, use the following command:  

```ps
Install-Package MSBuild.Version.Target
```

Or visit the [NuGet package page](https://www.nuget.org/packages/MSBuild.Version.Target/) for more details.  

---

## 🛠️ Usage Instructions

1. **Post-installation Setup**:  
   After installing the package, locate the `Version.txt` file in the **Properties** folder of your project. Update the file with your current project version in the SemVer format:  
   ```
   Major.Minor.Patch
   ```
   - **Major** and **Minor**: Managed manually.
   - **Patch**: Automatically incremented for non-`Release` builds.

2. **Configuration Management**:  
   The versioning logic activates during any build configuration **other than `Release`**. Ensure the appropriate configuration is selected:  
   - In Visual Studio, adjust this under **Build > Configuration Manager**.  
   - In CI pipelines or manual builds, specify the configuration explicitly using:  
     ```ps
     MSBuild /p:Configuration=Debug
     ```

3. **Build Process**:  
   During the build, the following updates occur automatically:  
   - `AssemblyInfo.cs`: The assembly version is updated to reflect the new version.  
   - `Version.txt`: The build version is incremented.  

---

## 📋 Example

Here’s a quick example of how the versioning would work:  
- Initial `Version.txt`:  
  ```
  1.0.0
  ```
- After a build with configuration `Debug`:  
  ```
  1.0.1
  ```
- After another `Debug` build:  
  ```
  1.0.2
  ```
- Build with configuration `Release`:  
  - Version remains unchanged.

---

## 🧩 Contributing

Contributions are welcome!  
Feel free to open issues, submit pull requests, or suggest features.  

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
