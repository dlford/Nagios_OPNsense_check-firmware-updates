# Nagios OPNsense check_firmware_updates

This is a Nagios plugin for checking software updates on OPNsense.

I've seen a few of these floating around, but none of them first ask OPNsense to look for available updates, they just check to see if OPNsense is aware of any updates.

This is written in bash for simplicity and portability, the only dependency is `jq`, which is available in most modern package managers.

## Installation

1. Copy `check_firmware_updates` to your Nagios scripts folder
2. Log in to your OPNsense machine and create a user with access to the firmware API only
3. Choose `/sbin/nologin` for the shell
4. Check the box for `generate a scrambled password`
5. Assign the privilege `System: Firmware`
6. Add an API key for the newly created user, you'll then have a `key` and `secret` to use for this check

## Usage

This script needs three inputs:

1. `-h`: The hostname or IP address of your OPNsense box
2. `-k`: Your API `key` from above
3. `-s`: Your API `secret` from above

Example: `/path/to/check_firmware_updates -h HOSTNAME -k API_KEY -s API_SECRET`
