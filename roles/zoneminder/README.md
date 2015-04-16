# ansible playbook to install zoneminder

This installs a pre-configured zoneminder system on top of a minimal debian installation.   It assumes that the debian installation has a pre-configured ssh known hosts file so that ansible can log in.   This playbook restores a database configuration that defines one monitor (my wifi webcam) and its zone configuration and filter (PurgeWhenFull enabled).

## Setup

    edit your ip address into hosts
    ensure your ~/.ssh/config loads the correct key for the remote host

## Installation

    # install just the 'zm2' test virtual machine
    ansible-playbook site.yml -i hosts --limit=zm2

## Testing

    open http://x.x.x.x/zm and see the monitor/zone/filter is working
    trigger an event and verify it is logged and viewable

## To Do List

this is idempotent, but the zoneminder tasks file is a bit ugly to say the least
