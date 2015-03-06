
NodeJS AdBlock Proxy
====================

NodeJS Proxy for blocking adverts on the interwebz (with support for Adblock Plus filter lists and /etc/hosts files).
This project aims to make the interwebz even moar awesome!


# Why using a NodeJS based AdBlock Proxy?

- It's blazing fast. Seriously, forget other Proxy implementations.
- It's written in JavaScript !!!!111eleven.

- With a few hours on Facebook, reddit, stackoverflow, it uses this amount of memory (whilst having over 20k blocked hosts and urls with n rulesets):

![Screenshot #01](./docs/images/screenshot_01.png)


- And yes, 15MB is way less than a couple GB memory usage of an AdBlock Plus Web Browser extension.
- If you still don't believe it, get over it and use something else. I don't care.


# License

This project is released under the WTFPL.
See the LICENSE.md for details.


# Installation

*Note*: You can change the suggested installation folder to whereever you want to install it.
Just make sure you change the paths in the bash commands accordingly.

- Download and install the newest available stable release of NodeJS from [nodejs.org](http://nodejs.org).

- Download this project via [zip-file](https://github.com/LazerUnicorns/nodejs-adblock-proxy/archive/master.zip) and extract its contents to **/opt/adproxy**.

- Navigate to the folder in your Shell (or PowerShell) and execute:

```bash
cd /opt/adproxy; # change if you used a different folder
nodejs ./bin/proxy; # will start a proxy on defaulted settings (localhost:8080)
```

# Settings

If you want to use customized parameters, these are the supported parameters and their functionality:

- --host=<ip> where *ip* is an IPv4 or IPv6 address (e.g. *192.168.0.1*)
- --port=<port> where *port* is a valid port number (e.g. *8080*)
- --public=true will allow using the proxy from other hosts (defaulted). Use --public=false to only allow connections using the given *ip*.
- --protocol=http will spawn an HTTP based proxy. Supported protocols are *http*, *socks5*.

```bash
# Example usage of customized parameters
nodejs ./bin/proxy --host=192.168.0.1 --port=8080 --public=false --protocol=http
```


# Features

- HTTP Proxy
- Host config files support (aka **/etc/hosts**)
- Adblock Plus filter list support ("without element hiding")
- Use the *./update.sh* (requires wget) to update all filter lists from predefined sources.


# Work-in-progress (aka still not working)

- HTTPS Proxy (automatic SSL certificate issueing, maybe via sniffing (aka nulling bug))
- SOCKS5 Proxy
- Support for ABP rules with $variable identifiers (requires HTML code parsing, which would slow down proxy)


# Usage

If you want to use another machine as a Gateway (for example on a Raspberry Pi), you can start the Proxy
on the machine with a reachable IP (e.g. *--host=192.168.x.x*) so that your own machine can connect
to it. If you don't know the IP of the machine (or want to host it on a domain-reachable server) you
can simply set the *--public=true* flag. See [Settings](#Settings) for more details.


## Ubuntu (Gnome Shell)

- Start the Proxy (as shown in [Installation](#Installation))
- Go to **System Settings** > **Network**
- Click on **Network Proxy** on the left side
- Select Method *Manual* and use 127.0.0.1 as IP and 8080 as port

If you started the Proxy setting a different port, please change that accordingly.

![Screenshot Gnome Shell](./docs/images/screenshot_gnome_shell.png)

## Mac OS X

- Start the Proxy (as shown in [Installation](#Installation))
- Go to **System Preferences** > **Network**
- Click on **Advanced** on the right side
- Navigate to **Proxies** menu tab
- Check the **Web Proxy (HTTP)** checkbox on the left side
- Fill in 127.0.0.1 as IP and 8080 as port
- Click **OK** and **Apply** to apply the settings

If you started the Proxy setting a different port, please change that accordingly.

![Screenshot Mac OS X](./docs/images/screenshot_mac_osx.png)

## TODO: Other Operating Systems

Documentation about setup on other Operating Systems.
**Contributions welcomed**.

