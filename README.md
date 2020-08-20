# square
Shell script to help circumvent Disney Circle.

# Suport

Right now this solution only works on macOS but if enough people open issues I'd be happy to look into getting it operational on other operating systems.

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

To toggle between going through Cirlce and circomventing it, all you have to do is run `./square`.

If you'd like to check if you are going through circle or not, just call `./square -s` (`-s` for status).

