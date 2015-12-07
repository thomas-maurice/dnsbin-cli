# dnsbin-cli
[![Build Status](https://travis-ci.org/thomas-maurice/dnsbin-cli.svg?branch=v0.0.1)](https://travis-ci.org/thomas-maurice/dnsbin-cli)
[![PyPi](https://img.shields.io/pypi/dm/dnsbin-cli.svg)](https://pypi.python.org/pypi/dnsbin-cli)
[![PyPI](https://img.shields.io/pypi/v/dnsbin-cli.svg)](https://pypi.python.org/pypi/dnsbin-cli)

This is the commandline for the dnsbin project (https://github.com/thomas-maurice/dnsbin)

# Using the commandline
To use the command line you need to install few packages using pip :
```bash
pip install requests dnspython clifactory
```

Or if you prefer you can install it from pip
```bash
pip install dnsbin-cli
```

## Posting a file
```bash
dnsbin post someserver.tld file_name
87597b44-d913-4740-9091-d9bd62b8f422
```

Note that if the file is not ascii only, it will be encoded
before being uploaded.

Done ! Your paste has id `87597b44-d913-4740-9091-d9bd62b8f422`

## Getting a paste
```bash
dnsbin get someserver.tld 87597b44-d913-4740-9091-d9bd62b8f422
Paste is 15 chunks long
 * Getting 1.87597b44-d913-4740-9091-d9bd62b8f422 chunk
 * Getting 2.87597b44-d913-4740-9091-d9bd62b8f422 chunk
  ... Some more chunks ...
 * Getting 14.87597b44-d913-4740-9091-d9bd62b8f422 chunk
 * Getting 15.87597b44-d913-4740-9091-d9bd62b8f422 chunk
Your paste :
 ... The text you did paste ! ...
```

## Encrypting a paste with AES
You can now encrypt pastes with AES. You have to use the following syntax :
```bash
dnsbin post 172.17.42.1 bin/dnsbin --aes
Encrypting paste with key Kfx0JPViOnQmhqRe
6e151dc9-ea37-421b-b635-d2fc0f4877a6
```

And you can retrieve it with :
```bash
dnsbin get 172.17.42.1 6e151dc9-ea37-421b-b635-d2fc0f4877a6 --key Kfx0JPViOnQmhqRe
```

Please note that the file will be padded to reach a lengh that is multiple of 16.
