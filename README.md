# Step by Step Guide to Set Up Anaconda & UV Environment for Data Science/AI

This is step-by-step tutorial for setting up a Data Science/AI environment using Anaconda and UV Environment. This tutorial is written with easy-to-follow step-by-step explanations.

---

## What is Anaconda and Conda?

**Anaconda** is an open-source distribution for the Python and R programming languages, designed for scientific computing, data analysis, and machine learning. Anaconda simplifies package and environment management and supports over 1,500 ready-to-use data science packages.  

**Conda** is a package and environment manager included in Anaconda. Conda allows users to manage packages and environments efficiently, avoid dependency conflicts, and ensure project consistency.

---

## ❓ Why Do We Need a Virtual Environment?

Virtual environments allow us to:

- Isolate projects: Each project has specific dependencies and package versions without affecting other projects.
- Prevent version conflicts: Avoid issues when two projects require different versions of the same package.
- Reproducibility: Ensure the code runs with consistent dependencies across different systems.

---

## What is UV?

UV is a Python environment management tool that allows you to easily create, manage, and delete virtual environments. Unlike pip and virtualenv, UV integrates environment creation and package installation in a single command, and provides automatic Python version management.

---

## Why Use UV?

- **Speed**: Faster package installation and dependency resolution compared to pip and poetry.
- **Ease of Use**: Simple and intuitive commands for creating and managing environments.
- **Python Version Management**: Ability to manage multiple versions of Python without additional tools.
- **Project Isolation**: Each project can have its own environment and dependencies, avoiding conflicts between projects.

---

## 🐍 Part 1: Installing Anaconda

**1. Download the Anaconda Installer**  
**What**  
The installer file to install Anaconda on your computer.  
**Why**  
Anaconda provides Python and ready-to-use data science packages in one installation.

Steps:
- Go to https://www.anaconda.com/products/distribution
- Choose the version for your OS (Windows/macOS/Linux)
- Click the Download button
![image](downloadAnaconda.png)
Do's:
- Download from the official Anaconda website
- Save the installer in an easily accessible folder  
Don'ts:
- Do not download from unofficial sources
- Do not save in system folders

**2. Run the Anaconda Installer**  
**What**  
The process of installing Anaconda on your system.  
**Why**  
To get Python and all necessary data science packages.

Steps:
- Open the downloaded installer
- Follow the installation wizard
- Choose the “Add Anaconda to PATH” option (optional)
![Image](installAnaconda.png)

Do's:
- Use default settings if unsure
- Check the PATH option for easier terminal access  
Don'ts:
- Do not change the installation directory to a system folder
- Do not cancel the installation midway

**3. Verify Anaconda Installation**  
**What?**  
This step ensures that Anaconda is properly installed and can be accessed from the terminal.  
**Why?**  
To prevent issues in the next steps when using Conda or Python from Anaconda.

Steps:
1. Open terminal or command prompt
2. Type the command: `conda --version`
3. If the Conda version appears, the installation is successful.
```
(base) deka@MBAir ~ % conda --version
conda 24.9.2
```
Do's:
- Use a new terminal session after installation to ensure PATH is refreshed
- Make sure the command runs without errors  
Don'ts:
- Don’t ignore errors or missing version output — check the installation again

**4. Configure Conda and Anaconda PATH Variables**  
**What?**  
Configuring PATH variables so the Conda and Python commands can be accessed from any terminal.  
**Why?**  
So you don't have to use Anaconda Navigator or a specific terminal every time.

Steps:
1. On Windows, add Anaconda and Scripts directory to the PATH Environment Variable.
2. On macOS/Linux, this is usually automatic. If not, edit `.bashrc` or `.zshrc`.
3. Press `Windows + R`, type `sysdm.cpl`, press Enter.
4. Go to the “Advanced” tab, click “Environment Variables”.
5. Choose “Path” in “System variables”, click “Edit”.
6. Add the following paths (replace USERNAME):
7. Click OK

Do's:
- Restart terminal after making changes
- Restart computer if necessary  
Don'ts:
- Don’t delete other important PATH entries
- Be careful while editing environment variables

**5. Create a New Conda Environment**  
**What?**  
Creating a new Conda environment means creating a separate workspace for a project.  
**Why?**  
To avoid conflicts between different Python or package versions across projects.

Steps:
- Run the following in terminal: `conda create -n env_name python=3.9`
```
(base) deka@MBAir Library % conda create -n dekaisn_env python=3.9
Channels:
 - defaults
Platform: osx-arm64
Collecting package metadata (repodata.json): done
Solving environment: done

## Package Plan ##

  environment location: /opt/anaconda3/envs/dekaisn_env

  added / updated specs:
    - python=3.9


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    ca-certificates-2025.2.25  |       hca03da5_0         131 KB
    expat-2.7.1                |       h313beb8_0         156 KB
    openssl-3.0.16             |       h02f6b3c_0         4.3 MB
    pip-25.1                   |     pyhc872135_2         1.3 MB
    python-3.9.23              |       h99c0cbc_0        12.5 MB
    setuptools-78.1.1          |   py39hca03da5_0         1.7 MB
    tk-8.6.14                  |       h6ba3021_1         3.3 MB
    tzdata-2025b               |       h04d1e81_0         116 KB
    wheel-0.45.1               |   py39hca03da5_0         115 KB
    xz-5.6.4                   |       h80987f9_1         289 KB
    ------------------------------------------------------------
                                           Total:        23.8 MB

The following NEW packages will be INSTALLED:

  bzip2              pkgs/main/osx-arm64::bzip2-1.0.8-h80987f9_6 
  ca-certificates    pkgs/main/osx-arm64::ca-certificates-2025.2.25-hca03da5_0 
  expat              pkgs/main/osx-arm64::expat-2.7.1-h313beb8_0 
  libcxx             pkgs/main/osx-arm64::libcxx-14.0.6-h848a8c0_0 
  libffi             pkgs/main/osx-arm64::libffi-3.4.4-hca03da5_1 
  ncurses            pkgs/main/osx-arm64::ncurses-6.4-h313beb8_0 
  openssl            pkgs/main/osx-arm64::openssl-3.0.16-h02f6b3c_0 
  pip                pkgs/main/noarch::pip-25.1-pyhc872135_2 
  python             pkgs/main/osx-arm64::python-3.9.23-h99c0cbc_0 
  readline           pkgs/main/osx-arm64::readline-8.2-h1a28f6b_0 
  setuptools         pkgs/main/osx-arm64::setuptools-78.1.1-py39hca03da5_0 
  sqlite             pkgs/main/osx-arm64::sqlite-3.45.3-h80987f9_0 
  tk                 pkgs/main/osx-arm64::tk-8.6.14-h6ba3021_1 
  tzdata             pkgs/main/noarch::tzdata-2025b-h04d1e81_0 
  wheel              pkgs/main/osx-arm64::wheel-0.45.1-py39hca03da5_0 
  xz                 pkgs/main/osx-arm64::xz-5.6.4-h80987f9_1 
  zlib               pkgs/main/osx-arm64::zlib-1.2.13-h18a0788_1 


Proceed ([y]/n)? y


Downloading and Extracting Packages:
                                                                                                                                               
Preparing transaction: done                                                                                                                    
Verifying transaction: done                                                                                                                    
Executing transaction: done                                                                                                                    
#                                                                                                                                              
# To activate this environment, use                                                                                                            
#                                                                                                                                              
#     $ conda activate dekaisn_env                                                                                                             
#                                                                                                                                              
# To deactivate an active environment, use                                                                                                     
#
#     $ conda deactivate
```
Do's:
- Use descriptive and easy-to-remember names for environments  
- Avoid unnecessary environment creation  
Don'ts:
- Don’t install all packages in the base environment

---

## 🧪 Part 2: Creating UV Environment

**1. Create a New Environment**  
**What**  
Create an isolated environment for a UV project.  
**Why**  
To prevent dependency conflicts across projects.

Steps:
1. Make sure Conda is deactivated (`conda deactivate`)
2. Type: `pip install uv`
3. A successful output like `Successfully installed uv-0.7.12` indicates success
4. The `ghost_intellixuv` folder will be created during `uv init`. You do not need to create it manually
```
(base) deka@MBAir Library % pip install uv
Collecting uv
  Downloading uv-0.7.13-py3-none-macosx_11_0_arm64.whl.metadata (11 kB)
Downloading uv-0.7.13-py3-none-macosx_11_0_arm64.whl (15.8 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 15.8/15.8 MB 9.5 MB/s eta 0:00:00
Installing collected packages: uv
Successfully installed uv-0.7.13
```

Do's:
- Use descriptive environment names
- Use compatible Python versions  
Don'ts:
- Don’t use the base environment for projects
- Don’t create unnecessary environments

**2. Initialize the UV Project**  
**What?**  
Initializing a UV project sets up the directory structure and basic config files.  
**Why?**  
Helps maintain consistency, supports collaboration, and ensures manageable dependencies.

Steps:
1. Ensure UV environment is active  
2. Run:  
   `uv init ghost_intellixuv`  
   `cd ghost_intellixuv`  
3. Output will indicate initialization at `/Users/deka/ghost_intellixuv`
```
(base) deka@MBAir ~ % uv init ghost_intellixuv 
Initialized project `ghost-intellixuv` at `/Users/deka/ghost_intellixuv`
```
```
(base) deka@MBAir ~ % cd ghost_intellixuv 
(base) deka@MBAir ghost_intellixuv %
```
Do's:
- Use consistent folder structure  
- Document dependencies in `requirements.txt`  
- Create a clear `README.md`  
- Use a virtual environment per project  
Don'ts:
- Don’t mix project files with personal files  
- Don’t forget to add environments to `.gitignore`  
- Don’t store sensitive data in the project folder  
- Don’t change folder structure after setup

**4. Install Required Packages**  
**What?**  
Install the necessary libraries for the UV project.  
**Why?**  
To access the functions needed during development.

Steps:
- Type: `uv add pandas`
```
(base) deka@MBAir ghost_intellixuv % uv add pandas
Using CPython 3.12.7 interpreter at: /opt/anaconda3/bin/python3.12
Creating virtual environment at: .venv
Resolved 7 packages in 610ms
Prepared 6 packages in 1.82s
Installed 6 packages in 50ms
 + numpy==2.3.0
 + pandas==2.3.0
 + python-dateutil==2.9.0.post0
 + pytz==2025.2
 + six==1.17.0
 + tzdata==2025.2
```

Do's:
- Only install needed packages  
- Check for version compatibility  
Don'ts:
- Don’t install packages in base environment  
- Don’t install unknown packages blindly  
- Don’t mix UV and pip commands

**5. Deactivate UV Environment**  
**What?**  
Deactivate UV environment when done.  
**Why?**  
To return to base or default shell.

Steps:
- Type: `.venv\Scripts\deactivate`

Do's:
- Always deactivate when changing contexts  
Don'ts:
- Don’t leave environments active unnecessarily

**6. Conda vs UV Comparison**  
**What?**  
Compare Conda and UV environment management tools.  
**Why?**  
To choose the right tool based on needs.

Details:
- Conda: General-purpose environment and package management across projects  
- UV: Project-specific environment/framework, possibly focused on AI

Do's:
- Use Conda for broader environment control  
- Use UV for focused project setups  
Don'ts:
- Don’t mix configurations without syncing

**7. Recommended Packages for UV Environment**  
Common and recommended packages for data science and machine learning:
- numpy  
- pandas  
- matplotlib  
- scikit-learn  
- jupyter  
- seaborn  
- tensorflow or pytorch (as needed)
![image](https://private-user-images.githubusercontent.com/211091720/453819074-d4e68cf5-e066-44b5-bfb6-f070e9b755f1.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDk4NDAyNjUsIm5iZiI6MTc0OTgzOTk2NSwicGF0aCI6Ii8yMTEwOTE3MjAvNDUzODE5MDc0LWQ0ZTY4Y2Y1LWUwNjYtNDRiNS1iZmI2LWYwNzBlOWI3NTVmMS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNjEzJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDYxM1QxODM5MjVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wMmFlYTFiODM1OGVhZGExOTk3OWVlOWQzOTkxMjdlNjA4N2M0OTY2NDUxMjBmZjk0ODRiNTYzY2I5MTMyNWRkJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.SdcpLGH8PID1wf7yWeeSWb1g_7xD8UyjA4ee7CUcIrQ)
Do's:
- Install based on actual project needs  
- Regularly update packages  
Don'ts:
- Don’t install unnecessary or unknown packages

**8. Troubleshooting Guide for Conda and UV**  
Common issues and solutions:

*Issue 1: Conda Command Not Recognized*  
Symptom: `'conda' is not recognized`  
Solution:
- Verify Anaconda installation
- Check PATH variable
- Run `conda init cmd.exe` and restart terminal

*Issue 2: Environment Activation Fails*  
Symptom: `Script execution is disabled`  
Solution:
- Run PowerShell as Administrator  
- Type: `Set-ExecutionPolicy RemoteSigned`  
- Choose "Y"

*Issue 3: Package Installation Fails*  
Symptom: `Could not find a version`  
Solution:
- Update pip: `python -m pip install --upgrade pip`
- Check Python compatibility
- Try different package versions

Do's:
- Always read documentation and error messages  
- Use community forums and Stack Overflow  
Don'ts:
- Don’t ignore error messages  
- Don’t force install without checking

---

## 🔄 Part 3: Environment Management

Important Commands  
Below are some key commands for managing environments:
![image](https://private-user-images.githubusercontent.com/211091720/453810486-5eec8061-abef-4564-b5eb-31bb6c6bcad6.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDk4NDAyNjUsIm5iZiI6MTc0OTgzOTk2NSwicGF0aCI6Ii8yMTEwOTE3MjAvNDUzODEwNDg2LTVlZWM4MDYxLWFiZWYtNDU2NC1iNWViLTMxYmI2YzZiY2FkNi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNjEzJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDYxM1QxODM5MjVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02NzYwZmJmMTRjZTg2MWY4NDU0ZTU1ZjViM2I1NzkyYzY2NjYyNWRhNDMwNzNjODk2MmQwMDU0YjZhMDA0NzIyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.gmR0yFWu48yIBJeddoZSHF_B5l7yGT1KxOIsDG2earY)
- `conda create -n myenv python=3.9` — Create a new Conda environment
- `conda activate myenv` — Activate the Conda environment
- `conda deactivate` — Deactivate the current environment
- `conda list` — List installed packages
- `conda env remove -n myenv` — Remove environment

---

## 🎯 Conclusion

Anaconda is like a big city divided into buildings (environments), each with different furniture (packages) tailored to its inhabitants. You, as the user, can enter the right building depending on your task — avoiding interference with others.

By following this guide, you now have:

- Anaconda installed on your system  
- UV environment ready to use  
- Basic knowledge of environment management  

**Happy coding! 🚀**
