# square
Small Shell script to help circumvent Disney Circle.

# Support

Right now, this solution only works with macOS and Linux. Linux will need a few adjustments.

# Setup

First you must have `brew` installed, you can do this by running:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Next you can use `brew` to install `arping`:

```sh
brew install arping
```

Finally, you may have to add `export PATH=/usr/local/sbin:$PATH` to your `.bashrc` file, if `arping` cannot be found.

# Usage

To toggle between going through Circle and circomventing it, all you have to do is run `./square`.

If you'd like to check if you are going through circle or not, just call `./square -s` (`-s` for status).

If you'd like to manually use a different MAC address to add to the arp table, run `./square -m` (`-m` for manual mode).

# How it Works

The Circle device uses a method called ARP Spoofing, which in short, means one device pretends to be another device.

In this script, we try to add a static ARP Entry, which unless the root user deletes it, never changes.

## More details about ARP Spoofing

ARP (Address Resolution Protocol) is a protocol to resolve IP Addressses to MAC Addresses to connect to the internet.

Whenever your device wants to connect to a gateway IP, it looks at its ARP table to see where to connect to. But you might ask, "How does the device fill up the ARP table?" Good question. \
Routers and other similar devices send what seems to be an ARP Message with its ARP table entry, and there is no verification for this process. \
That means if a device sends an ARP table entry with the same IP Address as another device, it'll be treated as an "update". See the problem now? \
ARP Spoofing exploits this flaw and the only way to prevent ARP Spoofing is to have a static ARP entry.

Most of this info was taken from Wikipedia and some Reddit posts. This isn't a full explantion of the full ARP process, research on your own for more information.
