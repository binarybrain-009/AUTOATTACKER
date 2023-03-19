# GPT-Terminal-Bridge

## General
The goal is to build a user-friendly bridge to automate ChatGPT and other GPT modules to automatically control terminal-based applications. This allows an automation of many human-intensive works, such as penetration testing with tools.

There are two modes of running. One is based on the project `chatgpt-wrapper`, which uses playwright browser to extend the ChatGPT API. It is recommended for free users because other API libraries cannot bypass the Cloudflare protection. The other mode is API-based, which utilizes `utils/chatgpt.py`. ChatGPT plus user can provide necessary key information to use this mode. 

## Installation
1. Install `requirements.txt` with `pip install -r requirements.txt`
2. Install `chatgpt-wrapper`: `pip install git+https://github.com/mmabrouk/chatgpt-wrapper`. More details at: https://github.com/mmabrouk/chatgpt-wrapper.


## Examples
1. **Test Example with ChatGPT Browser**: `python3 example_chatgpt_playwright.py`
2. **Test Example with ChatGPT API** (requires API key): `python3 example_chatgpt_API.py`

