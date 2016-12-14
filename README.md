# MSBuild Artifactory Plugin

## Overview
Artifactory brings Continuous Integration to MSBuild, TFS and Visual Studio through the MSBuild Artifactory Plugin. This allows you to capture information about deployed artifacts, resolve Nuget dependencies and environment data associated with MSBuild build runs, and deploy artifacts to Artifactory. In addition, the exhaustive build information captured by Artifactory enables fully traceable builds.

## Installation and usage instructions
The full MSBuild Artifactory Plugin documentation is available [here](https://www.jfrog.com/confluence/display/RTF/MSBuild+Artifactory+Plugin).

## Debuging the Plugin using VS
  1. Creaet a new project.
  2. Add the Artifactory template as described in the Artifactory MS-Build [documentation](https://www.jfrog.com/confluence/display/RTF/MSBuild+Artifactory+Plugin).
  3. Change the AssemblyFile path of the JFrog.Artifactory.ArtifactoryBuild task in the Deploy.targets file.
    The new AssemblyFile path should points to the JFrog.Artifactory.dll which was craeted during the msbuild-artifactory-plugin build.<br/>
    For example: ```<UsingTask TaskName="JFrog.Artifactory.ArtifactoryBuild" AssemblyFile="%MS_Build_Project_Path%\msbuild-artifactory-plugin\lib\JFrog.Artifactory.dll" /> ```
  4. Close the project.
  5. Open the msbuild-artifactory-plugin.
  6. Right click on the msbuild-artifacoty-plugin --> properties
  7. Go to the Debug section.
  8. Change the start action to: “Start external program” and set in the full path to MSBuild.exe
  9. Add the project.sln and the working directory of the project you configured at the first step as command line arguments.
  10. Save and Close the properties.
  11. Now you can debug the deploy task.
    
  
