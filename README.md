# AUTOATTACKER

AUTOATTACKER IMPLEMENTATION

<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

<!-- PROJECT LOGO -->

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation on macOS](#installation-on-macos)
  - [1. Install Conda](#1-install-conda)
    - [For Intel Macs](#for-intel-macs)
    - [For Apple Silicon Macs (M1/M2)](#for-apple-silicon-macs-m1m2)
  - [2. Set Up the Conda Environment](#2-set-up-the-conda-environment)
  - [3. Install Project Dependencies](#3-install-project-dependencies)
  - [4. Verify the Installation](#4-verify-the-installation)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
  - [Common Issues and Solutions](#common-issues-and-solutions)
  - [Getting Help](#getting-help)

## Features

- Automates penetration testing tasks using AI.
- Integrates with various tools like sqlmap and playwright.
- Provides an interactive command-line interface.

## Prerequisites

- macOS (Intel or Apple Silicon)
- Python 3.10 (managed by Conda)
- Xcode Command Line Tools (for compiling packages)

## Installation on macOS

### 1. Install Conda

Conda is an open-source package and environment management system that simplifies package installation and management. We'll use Miniforge, a community-driven minimal installer for Conda, which is preferred for its simplicity and compatibility.

#### For Intel Macs

Download Miniforge for Intel Macs:

```bash
curl -LO https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-x86_64.sh

## Install Miniforge

```bash
bash Miniforge3-MacOSX-x86_64.sh
```
- Follow the on-screen prompts.
- Accept the license agreement.
- Choose the installation location (default is recommended).
- Allow the installer to initialize Conda.
- Restart Terminal to apply changes.

### For Apple Silicon Macs (M1/M2)

Download Miniforge for Apple Silicon Macs:

```bash
curl -LO https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh
```

Install Miniforge:

```bash
bash Miniforge3-MacOSX-arm64.sh
```
- Follow the on-screen prompts.
- Accept the license agreement.
- Choose the installation location (default is recommended).
- Allow the installer to initialize Conda.
- Restart Terminal to apply changes.

## 2. Set Up the Conda Environment

Create a New Conda Environment with Python 3.10:

```bash
conda create -n pentestgpt_env python=3.10
```

Activate the Conda Environment:

```bash
conda activate pentestgpt_env
```

Verify the Python Version and Architecture:

```bash
python --version
python -c "import platform; print(platform.machine())"
```
- Ensure the Python version is 3.10.x.
- For Intel Macs, `platform.machine()` should return x86_64.
- For Apple Silicon Macs, it should return arm64.

## 3. Install Project Dependencies

Before installing dependencies, ensure you have Xcode Command Line Tools installed, as some packages require compilers.

### Install Xcode Command Line Tools

```bash
xcode-select --install
```
- Follow the prompts to complete the installation.

### Navigate to the Project Directory

If you haven't cloned the repository yet:

```bash
cd pentestgpt
```

### Install Dependencies with Conda and Pip

Some packages are available via Conda, and others via Pip.

#### Install Dependencies via Conda:

```bash
conda install -c conda-forge \
  cffi \
  cryptography \
  greenlet \
  orjson \
  pydantic \
  sqlalchemy \
  lxml \
  pillow \
  numpy
```

#### Install Remaining Dependencies via Pip:

```bash
pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
```

If your project uses Poetry, install dependencies using Poetry:

```bash
pip install poetry
poetry install
```
*Note: Ensure that `pyproject.toml` is present in the project directory.*

## 4. Verify the Installation

Activate the Conda environment (if not already active):

```bash
conda activate pentestgpt_env
```

Run the Application:

```bash
pentestgpt-connection
```

If the command is not found, ensure that the package scripts are installed correctly. You might need to adjust your `PATH` or run the application using Python:


### Test Specific Commands:

```bash
pentestgpt-connection
```

## Usage

After successful installation, you can start using AutoAttacker by running:

```bash
python autoattacker.py
```

Follow the on-screen instructions to interact with the tool.

## Troubleshooting

### Common Issues and Solutions

1. **pip Command Not Found**
   Ensure that you have activated the Conda environment:
   ```bash
   conda activate pentestgpt_env
   ```

2. **Architecture Mismatch Errors**
   If you receive errors related to architecture mismatch (e.g., trying to install packages built for `arm64` on `x86_64`), ensure that:
   - You're using the correct Miniforge installer for your Mac's architecture.
   - Your terminal is not running under Rosetta (for Apple Silicon Macs).

3. **Compilation Errors During Package Installation**
   Some packages require compilation from source. Ensure that:
   - Xcode Command Line Tools are installed:
     ```bash
     xcode-select --install
     ```
   - You have installed necessary build dependencies via Conda.
   - Rust is installed for packages like `orjson` and `tiktoken`:
     ```bash
     curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
     source $HOME/.cargo/env
     ```

4. **Issues with playwright Installation**
   For `playwright`, you might need to install browser binaries:
   ```bash
   playwright install
   ```

5. **Environment Activation Issues**
   If the Conda environment doesn't activate properly, try initializing Conda for your shell:
   ```bash
   conda init $(basename $SHELL)
   source ~/.bashrc  # or ~/.zshrc depending on your shell
   ```

### Getting Help

- **GitHub Issues**: Open an issue at [GitHub Issues](https://github.com/user/repo/issues) for assistance.

## Note: The setup and config is based on a windows laptop that i currently use and depending on your command line setup and other system setting the configuration and system setup might differ
## Setup and Configuration

1. Set PowerShell Execution Policy:
   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
## Setup in VSCode
   
- PS C:\Users\cghdhv\venv> cd venv
- PS C:\Users\cghdhv\venv> .\Scripts\Activate.bat
- PS C:\Users\cghdhv\venv> .\Scripts\activate
- pip3 install -e .
## Setup in VSCode for environment variables
- $Env:OPENAI_KEY = ''
- $Env:PINECONE_API_KEY = ''
## check connection in VS-code
- PS C:\Users\cghdhv\venv> pentestgpt-connection
## Create a Pinecone account
- Get the API key
- Setup index, check for the settings in vectorDB.py, and update the parameters there if needed. 
## check Experience Manager working
- python TestExperienceManger.py
- This will check the working of Experience mainly dependent on the VectorDB.py implementation
## AutoAttacker Pipeline
- There are two auto attacker pipelines one is using GPT-4 and the other using ThinkGPT, autoattacker.py, and autoattacker_thinkGPT.py
- They can be run after experience manager's working has been tested 
## The file logs will be stored in the pentestgpt/config/logs/ folder