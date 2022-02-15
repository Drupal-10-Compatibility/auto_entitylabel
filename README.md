# How to use this template

This template can be used to quickly scaffold a Drupal project (module, theme, profile, etc.) to begin remediating code for Drupal 10 Compatibility.

## How to use this template to create a starter project

1. Click the "Use this template" button in the menubar
1. On the "Create a new repository from _project-tempalte" page, change the owner to "Drupal-10-Compatibility", and in the "Repository name" field, add the machine name of the project as it is specified on Drupal.org.
1. Select "public" repository
1. Click Create repository from template
1. Wait until your project is created, then clone the project locally (follow next instructions)

## After creating your project and cloning your repository locally...

### Gather information
1.  Visit the project page for the selected project on Drupal.org
1.  Note the most recent D8 or D9 dev version of the project (usually found under "Releases", in the format of "8.x-1.x-dev, or "3.2.x-dev")
1.  Make a note of the machine name of the project (listed after `https://www.drupal.org/project/` in the page URL).
1.  Make a note of the Human Readable project name, which is the displayed name of the project on the page, below the tabbed menu which is directly below "Download & Extend".

### README.md
1.  Edit the `README.md` file, replacing `<Insert Project Name here>` with the human readable name of the Drupal project, and replace all occurrences of `<project_name>` with the machine name of the project.
1.  Remove all contents of the `README.md` file down to the comment below these instructions, and save the `README.md` file

### DDEV config file and custom commands
1.  Edit the `.ddev/config.yaml` file, and replace all occurrences of `<project_name>` with the machine name of the project (there is one occurrence in this file), replacing any `_` in the machine name with a `-` to create a valid project name for DDEV
1.  Replace all occurrences of `<project_machine_name>` with the machine name of the project, leaving the `_` as is in the machine name, and save.

### Github Actions
1.  Edit the `./github/workflows/coding_standards.yml` file, and replace all occurrences of `<project_name>` with the machine name of the project (there are two occurrences by default in this file), and save.
1.  Edit the `./github/workflows/static_analysis.yml` file, and replace all occurrences of `<project_name>` with the machine name of the project (there are two occurrences by default in this file), and save.
1.  Edit the `./github/workflows/unit_tests.yml` file, and replace all occurrences of `<project_name>` with the machine name of the project (there are two occurrences by default in this file), and save.

### composer.json
1.  Edit the composer.json file, and replace all occurrences of `<project_name>` with the machine name of the project (there are two occurrences by default in this file), and save.
1.  Replace `<human readable project name>` with the name of the project from Drupal.org, and save the `composer.json` file.
1.  At the command line, execute `composer require drupal/<project_name>:#.x-dev`, replacing `<project_name>` with the machine name of the project, and replacing `#` with the main version number of the project you intend to remediate for coding standards compliance (which was gathered from the project page on Drupal.org as the dev version)

### Wrap up
1.  Commit all changes to the files in the project to the repository, and push up your changes.
1.  You're all set and ready to go.  Github actions will run coding standards checks, static analysis for deprecations, and execute any unit tests that the project has in it's codebase.
1.  Work on code remediation in the form of patches until all Github Actions jobs execute successfully.
1.  Submit your patches to the project on Drupal.org!


## Working on the project locally with DDEV
1.  Execute `ddev install` to install a working copy of Drupal with this project for unit testing purposes

### Unit Tests
1.  


Welcome to the Drupal Community, we appreciate your contributions :). Happy Coding!

<!-- Delete all lines above here when creating a project from this template, after following the above instructions -->
# <Insert Project Name here>

## Overview

The purpose of this project is to leverage Github Actions to build a Drupal 10 site, install the above module, and conduct the following:

* Static Analysis:  Use phpstan-drupal extension for phpstan to conduct a static scan of the module codebase for deprecations for both PHP 8 and Drupal 10.
* Coding Standards:  Check for compliance with Drupal Coding Standards.
* Unit Tests:  Execute any unit tests included in the module's codebase to make sure that unit testing integrity is intact after patching for deprecations and coding standards compliance.

## Test Results

| Analysis Type | Results | Test Run |
| ----- | ----- | ----- |
| Static Analysis: | ![Static Analysis](https://github.com/Drupal-10-Compatibility/<project_name>/actions/workflows/static_analysis.yml/badge.svg) | [Static Analysis](https://github.com/Drupal-10-Compatibility/<project_name>/actions/workflows/static_analysis.yml) |
| Coding Standards: | ![Coding Standards](https://github.com/Drupal-10-Compatibility/<project_name>/actions/workflows/coding_standards.yml/badge.svg) | [Coding Standards](https://github.com/Drupal-10-Compatibility/<project_name>/actions/workflows/coding_standards.yml) |
| Unit Tests: | ![Unit Tests](https://github.com/Drupal-10-Compatibility/<project_name>/actions/workflows/unit_tests.yml/badge.svg) | [Unit Tests](https://github.com/Drupal-10-Compatibility/<project_name>/actions/workflows/unit_tests.yml) |
