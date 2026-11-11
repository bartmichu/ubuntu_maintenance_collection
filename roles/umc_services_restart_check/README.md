# umc_services_restart_check

## Description

Checks for services requiring restart.

## Requirements

- Target hosts must have `needrestart` installed.

## Role Variables

This role does not use any input variables.

This role sets the following host facts:

- `_umc_global_services_to_restart`
