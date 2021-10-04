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

## To create your own project based on the template 

1. Fork the `chgpu_agave_template` repo from github by clicking the `Fork` button on the upper-right corner
2. In the forked repo, click the `Settings` button, and then rename the repo with a concise but meaningful project name, e.g., "sample_prep".
3. **On your own computer**, clone the new repo. 
4. Rename the `cpp`,`json`, `sh` files with your project name. 
   For example, `repose.cpp` --> `sample_prep.cpp`; `repose.json` --> `sample_prep.json`; and `repose.sh` --> `sample_prep.json`
5. Edit the source `cpp` and `json` files for your project.
6. Update the `CMakeList.txt` file:

   Replace the word `repose` with your project name.

   For example, change

```CMake
set(MY_PROJECT repose)
```
to

```CMake
set(MY_PROJECT sample_prep)
```
7. Update the `repose.sh` file

  * Search and replace all instances of `repose` with your project name, e.g., `sample_prep`
  * Update the slurm requests as shown in the example bash script.

8. Commit the changes and push to the github repo.

```bash
git add --all
git commit -m 'update to sample_prep'
git push
```
9. Repeat the steps the same as in the "test run" example above, except that you work on the new project repo.









