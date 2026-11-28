# Local development notes

## Scope

This repository contains the approximately 5% complete PCS prototype. Existing scripts and Docker files are retained with the application baseline. Their entry-point and import integration needs correction before they can be presented as verified launch commands.

This package prepares the complete source and GitHub presentation. For updating an existing checkout, use [Update GitHub](../UPDATE-GITHUB.md).

## Prepare an isolated development environment

From the repository root, use a Python 3.11 environment matching the supplied Docker baseline:

    python3.11 -m venv .venv
    source .venv/bin/activate
    python -m pip install -r requirements.txt

These are the repository's existing dependency pins, not an assertion that dependency completeness or compatibility has been fully validated.

## Check syntax without starting the service

    python -m compileall -q codes config

Syntax validation does not verify imports, application startup, routes or transaction behaviour.

## Before running the prototype

An implementation pass must reconcile package-relative imports and dynamic module loading with the hyphenated source filenames. It must align the startup scripts and container commands with that resolved entry point, complete missing dependencies where identified, and verify configuration and persistent storage paths.

The prior documentation used an underscored module path that is not supplied as a matching source file. Do not treat that earlier command as a validated local launch path. [Implementation](implementation.md) explains the module responsibilities.

Once the entry point is integrated, validate startup and the sample purchase/receipt/confirmation flow in a disposable development data directory. Use only test participants and synthetic payment evidence while validating the prototype.

## Runtime state

The application uses data/ for JSON records and model storage, and uploads/ for participant media and receipt files. The source package contains the tracked model files and empty-directory placeholders; it does not supply real participant accounts, receipts or transaction databases.

Keep existing runtime JSON, uploads, environment configuration and local Git metadata when applying this presentation update. No data reset is needed to replace the README and image assets.

## Containers and server configuration

The Docker and Apache files remain in [docker/](../docker/) and [config/](../config/). Their presence does not establish a validated production deployment. See [Production readiness](production.md) for the implementation boundary.
