# Mythic Witches
An open source module for Mythic Bastionland. This repository contains everything needed to make your own version of the module and is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)

**View the latest published PDF [HERE](published/mythic-witches-0.1.1-preview.pdf).**

## Structure
To make things simple, most of the conent of the module is managed separately from the formatting configuration as spreadsheets in google sheets (configured in the projects.yaml file). This makes working on repetitive format content (i.e. Witches and Myths) simple and easy to manage (especially with multiple collaborators). These sheets are pulled into the libary on-demand at render time and are periodically committed for proper versioning.

Formatting of the content is accomplished via Latex for singleton content (i.e. the rules addendum) and jinja2 templated Latex for repetitive format content (i.e. Witches and Myths). Mapping between sheets and templates is defined in the projects.yaml file and all templates are applied per-row. Templates and the main tex file heavily leverage latex commands defined in the class file to keep the layout clean where possible. This also makes re-styling of the content simpler.

Images are stored in the images directory and are stored via git LFS to reduce repository slowdowns. All images used should be labeled with a source description in the source sheets to ensure that usage is valid from a licensing perspective.

## Rendering the module locally
### Prerequisites
- Install a modern LaTex distribution which provides pdflatex
    - Mac: [MacTex](https://www.tug.org/mactex/)
    - Ubuntu: run `sudo apt install texlive-full`
- Install python
    - Mac (with homebrew): run `brew install python`
    - Ubuntu: run `sudo apt install python3`
- Install python dependencies
    - Run `pip install -r publishing-tools/scripts/requirements.txt`
### Running the render command
- Run `publishing-tools/scripts/render.py mythic-witches`
    - Optionally pass `--refresh` to refresh tables from source

The rendered result will be available as `projects/mythic-witches/pdf/mythic-witches.pdf`