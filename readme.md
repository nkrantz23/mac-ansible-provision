mac-local-provision
------

[![pipeline status](https://gitlab.com/quietshelf-public/mac-local-provision/badges/master/pipeline.svg)](https://gitlab.com/quietshelf-public/mac-local-provision/pipelines)

NOTE: This has not been tested on a fresh machine yet nor does it have any support outside of the latest OSx distro.

## What this does

This will set up a local machine with your basic environments for development:

- homebrew
- ansible
- python

#### Future Support

- git
- docker
- rbenv
- nvm
- virtualenv
- php

## Getting Started

1. `make` - run this to get Brew/Python/Ansible dependencies.
2. `make provision`

### What you shouldn't do

Often its better to run parts of your development stack on your host machine, for performance or ease of use reasons. A good example is having your front-end pipeline (e.g webpack, npm, gulp, watchers, etc) running on the host so your feedback on HMR/live reload is as quick as possible.

To keep your machine clean and maximize the dev/prod parity I highly recommend:

- Use Docker for databases, caches, search engines, and other data stores.
- Use Docker for networking or routing.
- Use Docker for your back-end if possible.
- Your CI/CD builds should build a container on EVERY push.
- Your CI/CD builds should smoke test your built containers.
- Your staging => production pipeline should be container based.

Keep in mind this is how I currently like to work. It's not perfect for everyone, just keep the message in mind.
