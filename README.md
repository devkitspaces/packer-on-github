# Packer with GitHub Actions

Experimenting with GitHub Actions for building machine images with Packer. Ideally trying to figure out what it takes for building the following on GitHub Actions:

- VirtualBox ISO
- Hyper-V ISO
- Docker Image

## Docker Image

A base case. I want to confirm that I am in fact able to use packer without issue on GitHub Actions.

## HyperV

I have had to do some work with Windows containers recently, and have found them to have performance issues for disk intense work. I was curious, if some of the provisioning scripts for the docker container could be used in a HyperV machine. That would allow for some performance experimentation between the two types.

## VirtualBox

One of my previous projects involved using Vagrant to provision desktop environments. The problem with those environments is that the provisioning process was not hermetic. Building the same commit a month apart could result in significantly different images, or even failures. This was not ideal, so I wanted to investigate building images (ISOs) and using the Vagrantfile for environment configuration (e.g. ISO = environment, Vagrantfile = how you connect to this environment).

At the time I didn't like the available options for CI/CD, so decided to shelve the idea for now. With GitHub Actions, I'm curious if I would be able to build these images, then deploy them to something like VagrantCloud.
