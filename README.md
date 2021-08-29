# koel [![e2e](https://github.com/koel/koel/workflows/e2e/badge.svg)](https://github.com/koel/koel/actions?query=workflow%3Ae2e) [![unit](https://github.com/koel/koel/workflows/unit/badge.svg)](https://github.com/koel/koel/actions?query=workflow%3Aunit) ![Code Quality](https://scrutinizer-ci.com/g/phanan/koel/badges/quality-score.png?b=master) [![codecov](https://codecov.io/gh/koel/koel/branch/master/graph/badge.svg)](https://codecov.io/gh/koel/koel) [![OpenCollective](https://opencollective.com/koel/backers/badge.svg)](#backers) [![OpenCollective](https://opencollective.com/koel/sponsors/badge.svg)](#sponsors)

![Showcase](https://user-images.githubusercontent.com/8056274/115028055-bc02a280-9ec4-11eb-991c-69cd2a45b69c.png)

## Intro

**Koel** (also stylized as **koel**, with a lowercase k) is a simple web-based personal audio streaming service written in [Vue](http://vuejs.org/) on the client side and [Laravel](http://laravel.com/) on the server side. Targeting web developers, Koel embraces some of the more modern web technologies – CSS grid, audio, and drag-and-drop API to name a few – to do its job.

## Install and Upgrade Guide

For system requirements, installation/upgrade guides, troubleshooting etc., head over to the [Official Documentation](https://docs.koel.dev).

## Development

Since Koel makes use of [git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules), you'll want to make sure the submodule is up-to-date:

```bash
git pull
git submodule update --init --recursive --remote

# install the submodule dependencies
cd resources/assets
yarn install
```

To start the **PHP dev server**, which serves as the API of the application, run the following command from the root directory. By default, the server will listen at port `8000`.

```bash
php artisan serve
```

For the **client application** itself, run this command:

```bash
yarn hot
```

A development version of Koel should now be available at `http://localhost:8080` with full support for hot module reloading.

Alternatively, you can start both the PHP server and the client application in one go with `yarn dev`, which uses [`start-server-and-test`](https://github.com/bahmutov/start-server-and-test) under the hood.

## Testing, Linting, Static Analysis and Stuff

```bash
# PHP-related code quality tasks
# Basically, take a look at the "scripts" section in composer.json
composer test        # Run the PHP test suite
composer cs          # Run code style checker
composer cs:fix      # Run code style fixer 
composer analyze     # Run PHP static analysis

yarn build # Build a production version of the client application

# Client/E2E code quality tasks
# You may want to run `yarn build` first.
yarn test:e2e        # Run the Cypress test suite interactively
yarn test:e2e:ci     # Run the Cypress test suite non-interactively (CI mode)
# These commands need to be run from within the submodule (resources/assets)
yarn lint            # Lint
yarn type-check      # TypeScript type checking
yarn test            # Unit testing
```