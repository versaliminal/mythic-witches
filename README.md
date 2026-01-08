# mythic-witches
An open source module for Mythic Bastionland. This repository contains everything needed to make your own version of the module and is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)

# Rendering the module locally
## Prerequisites
- Install a modern LaTex distribution which provides pdflatex
    - Mac: [MacTex](https://www.tug.org/mactex/)
    - Ubuntu: run `sudo apt install texlive-full`
- Install python
    - Mac (with homebrew): run `brew install python`
    - Ubuntu: run `sudo apt install python3`
- Install python dependencies
    - Run `pip install -r publishing-tools/scripts/requirements.txt`
## Running the render command
- Run `publishing-tools/scripts/render.py mythic-witches`
    - Optionally pass `--refresh` to refresh tables from source

The rendered result will be available as `projects/mythic-witches/pdf/mythic-witches.pdf`
