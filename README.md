# Automatic Entity Label

## Overview

The purpose of this project is to leverage Github Actions to build a Drupal 10 site, install the above module, and conduct the following:

* Static Analysis:  Use phpstan-drupal extension for phpstan to conduct a static scan of the module codebase for deprecations for both PHP 8 and Drupal 10.
* Coding Standards:  Check for compliance with Drupal Coding Standards.
* Unit Tests:  Execute any unit tests included in the module's codebase to make sure that unit testing integrity is intact after patching for deprecations and coding standards compliance.

## Test Results

| Analysis Type | Results | Test Run |
| ----- | ----- | ----- |
| Static Analysis: | ![Static Analysis](https://github.com/Drupal-10-Compatibility/auto_entitylabel/actions/workflows/static_analysis.yml/badge.svg) | [Static Analysis](https://github.com/Drupal-10-Compatibility/auto_entitylabel/actions/workflows/static_analysis.yml) |
| Coding Standards: | ![Coding Standards](https://github.com/Drupal-10-Compatibility/auto_entitylabel/actions/workflows/coding_standards.yml/badge.svg) | [Coding Standards](https://github.com/Drupal-10-Compatibility/auto_entitylabel/actions/workflows/coding_standards.yml) |
| Unit Tests: | ![Unit Tests](https://github.com/Drupal-10-Compatibility/auto_entitylabel/actions/workflows/unit_tests.yml/badge.svg) | [Unit Tests](https://github.com/Drupal-10-Compatibility/auto_entitylabel/actions/workflows/unit_tests.yml) |

## Working on the project locally with DDEV

1. Execute `ddev start` and `ddev install` to install a working copy of Drupal
   with this project for unit testing purposes.
1. That command finishes with `ddev drush uli`, providing you with a one-time
   login link.
1. View the status of the installed project at Reports > Upgrade status
   (`/admin/reports/upgrade-status`).
1. Use `ddev` to list available commands. Use `ddev cmd --help` or `ddev help
   cmd` for more information on a specific command. This project defines at
   least the following custom commands:
   - `coding-standards`
   - `install`
   - `static-analyze`
   - `unit-tests`
