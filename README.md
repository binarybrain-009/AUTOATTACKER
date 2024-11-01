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



<!-- PROJECT LOGO -->





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

