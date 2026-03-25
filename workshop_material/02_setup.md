# 02 - Setup

# Table of contents

- [02 - Setup](#02---setup)
- [Table of contents](#table-of-contents)
  - [Install Miniforge](#install-miniforge)
    - [Check your OS](#check-your-os)
    - [Installing Miniforge](#installing-miniforge)
  - [Create a conda environment](#create-a-conda-environment)
  - [Clone this repo](#clone-this-repo)

## Install Miniforge

For this workshop, we will analyse our data using various software. However, the only software we will need to manually install is [Miniforge](https://conda-forge.org/miniforge/).

> **Why Miniforge and not Miniconda?**
> In 2023, Anaconda changed their Terms of Service so that using their package repository (the `defaults` channel) requires a paid license for organisations with 200 or more employees — which includes most universities. Miniforge is a community-maintained installer that uses the [conda-forge](https://conda-forge.org/) channel by default and is completely free for everyone. It installs the same `conda` command you are used to.

### Check your OS

If you already use Linux or macOS, great — skip to the next section!

If you use **Windows**, the easiest path is now [Windows Subsystem for Linux 2 (WSL2)](https://learn.microsoft.com/en-us/windows/wsl/install). WSL2 gives you a full Linux environment running natively inside Windows without needing a virtual machine.

To install WSL2, open PowerShell as Administrator and run:

```powershell
wsl --install
```

This installs Ubuntu by default. Once it is set up, open the **Ubuntu** app from the Start menu and follow the rest of this guide inside that terminal.

### Installing Miniforge

Download and run the Miniforge installer for your platform from the [Miniforge releases page](https://conda-forge.org/miniforge/).

On **Linux / macOS / WSL2** you can install with a single command:

```bash
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh
```

Follow the prompts and allow the installer to initialise conda in your shell. Restart your terminal afterwards.

Miniforge pre-configures `conda-forge` as the default channel, so no extra channel setup is needed. Just add the `bioconda` channel:

```bash
conda config --add channels bioconda
conda config --set channel_priority strict
```

## Create a conda environment

With Miniforge, we can create a conda environment which acts as a space contained from the rest of the machine in which our workflow will automatically install all the necessary software it uses, supporting the portability and reproducibility of your workflow.

Create a conda environment (called `demo_workflow_env`) that has Python and Snakemake installed (and all its dependent software)

```bash
conda create -n demo_workflow_env python=3.12 snakemake
```

Respond yes to the following prompt to install the necessary software in the new conda environment:

```bash
Proceed ([y]/n)?
```

Activate the conda environment we just created

```bash
conda activate demo_workflow_env
```

Now we can see which conda environment we are in on the command line

```bash
(demo_workflow_env) jlove@perennial:~$
```

*Snakemake has been installed within your `demo_workflow_env` environment, so you won't be able to see or use your Snakemake install unless you are within this environment*

## Clone this repo

To clone this repo (and use the example data I have provided), you will require you have git installed. See [this guide](https://www.atlassian.com/git/tutorials/install-git) for help with an installation of git.

Once git is installed, clone this repo with the following:

```bash
git clone https://github.com/leahkemp/RezBaz2026_snakemake_workshop.git
cd RezBaz2026_snakemake_workshop
```

See the [Git Guides](https://github.com/git-guides/git-clone) for information on cloning a repo

<p align="left"><b><a href="https://jloveuoa.github.io/RezBaz2026_snakemake_workshop/workshop_material/01_introduction.html">Previous page: 01 - Introduction</a>
<p align="right"><b><a href="https://jloveuoa.github.io/RezBaz2026_snakemake_workshop/workshop_material/03_create_a_basic_workflow.html">Next page: 03 - Create a basic workflow</a>
