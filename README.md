# Mythic Witches
An unoficial open source module for Chris McDowall's [Mythic Bastionland](https://chrismcdee.itch.io/mythic-bastionland). This repository contains everything needed to make your own version of the module and is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).

**View the latest published PDF [HERE](published/mythic-witches-0.1.1-preview.pdf).**

## Impetus and Philosphy
This project started from a love for Mythic Bastionland and a desire to explore the game concept in a few ways:
- If Knights are parts of the power structures of realms; what would it be like to play characters outside of those structures?
- If the concept of a Knight is significantly informed by combat ability, what would it be like to play characters unacustomed to it?

This lead to the concept of 'witches' as stand-ins for Knights and a narrative move away from war and rule and toward cunning and subterfuge. These are not witches in the traditional sense; they can be anyone who experiences an Omen and is awakened, chosing to live as an itenerant outsider following myths.

## Goals
This module is in continous development, but the end goal includes the following content.
- 20 Witch character classes
- 8 Myths
- 8 Events (single Omen Myths for worldbuilding/flavor)
- Blank character sheet template
- Multiple large random tables
- Lists of questions for world building

## Structure
### Content
To make things simple, most of the conent of the module is managed separately from the formatting configuration as spreadsheets in google sheets (configured in the projects.yaml file). This makes working on repetitive format content (i.e. Witches and Myths) simple and easy to manage (especially with multiple collaborators). These sheets are pulled into the libary on-demand at render time and are periodically committed for proper versioning.

Complex objects like random/choice tables and character blocks are defined in the sheets as yaml, which is automatically parsed into objects to be consumed at render time.

Singleton content (e.g. the rules addendum) is currently managed directly with the formatting, but it is possible this will change in the future.

### Formatting
Formatting of the content is accomplished via Latex, with jinja2 templates used for repetitive format content. Mapping between sheets and templates is defined in the projects.yaml file and all templates are applied per-row.

Templates and the main tex file heavily leverage latex commands defined in the class file to keep the layout clean where possible. This also makes re-styling of the content simpler.

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