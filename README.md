# build-unity-project-action
Used for building an Unity project using a specific installed version. Supports cross-platform.  

### Requirements
- **Unity Editor**: The specific Unity version required by your project is installed on the runner. The Unity license must be set to at least **Personal** or higher (Note: The **Unity Personal Version** license is not allowed).

### Inputs
- **unity_install_dir (Optional)**:  Root directory where Unity is installed. The action will search within this directory for the Unity version that matches the project’s requirements.
- **project_path (Required)**: Path to the Unity project root.
- **build_method (Required)**: The Unity build method to execute.
- **output_dir (Optional)**: Directory to store build outputs. Default is "Build/Releases".
- **log_name (Optional)**: Base name for the build log file. Default is "build_log".

### Usage
Here’s how to use this action in a GitHub workflow:  
```yaml
jobs:
  build-unity:
    runs-on: ubuntu-latest
    steps:
      - name: Build Unity Project
        uses: Wtzd8645/build-unity-project-action@master
        with:
          project_path: UnityProject
          build_method: MyGame.Editor.BuildScript.PerformBuild
          output_dir: Builds
          log_name: unity_build_log
```