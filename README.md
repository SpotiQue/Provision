# SpotiQue

This is a repository for provisioning.

## Usage

First, clone this repository using --recursive option.

You can use it for development, simply by running vagrant up.

To use it for production, you go to `provision` folder. You create `hosts` file.

Then you run `ansible-playbook site.yml -i hosts`. And after a while (first time takes up to 2.5 hours on RaspberryPi 1 Model B+),
you've got yourself this app set up. (after you've done a few steps from `core` repository).


