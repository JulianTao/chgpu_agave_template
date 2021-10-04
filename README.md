# A template ChronoGPU project to run on Agave

**Warning**: in order to use the google drive, you need to configure `rclone` first. 
See the workflow website for detailed information.


## To test run the template project, follow these steps:

1. Logon to the Agave cluster

```bash
ssh your.username@asu.agave.edu
```

2. Navigate to your workspace

   For example,

```bash
cd Workspace/Chrono
```

**Note**: Your working directory may be different from mine. It is recommended to have a directory called something like "Workspace" in your home directory to host all your projects

3. Clone this repo

```bash
git clone https://github.com/JulianTao/chgpu_agave_template.git
```

4. Navigate to the new directory

```bash
cd chgpu_agave_template
```
5. Examine the directory structure

```bash
ls -al
```
   It includes:

   * a CMakeList.txt
   * a bash file to be run by `sbatch`
   * a .gitignore file to ignore the output and log files for git operations
   * source files 
     * repose.cpp
     * GpuDemoUtils.hpp
     * repose.json
6. Edit `repose.sh` if needed, following the instructions inside

8. Run the bash file

```bash
sbatch repose.sh
```
8. Examine the `OUTPUT` directory and the log files `.err` and `.out`.
9. Examine the shared google drive, there should be a new folder data folder with the name specified in the bash script. 






