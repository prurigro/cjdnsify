# cjdnsify #

A wrapper for [force_bind](http://kernel.embedromix.ro/us/) that allows programs compatible with **ld_preload** to be restricted to the cjdns ipv6 address on a given cjdns tun device when run.

## Requirements ##

* **cjdns**: https://github.com/cjdelisle/cjdns
* **force_bind**: http://kernel.embedromix.ro/us/

## Usage ##

1. Copy `cjdnsify.conf` to `/etc/default/cjdnsify`.
2. Open `/etc/default/cjdnsify` and edit the variables to match the location of `force_bind.so` and name of your cjdns tun device on your system.
3. If **cjdroute** is running, you can now run **cjdnsify** with a command and its options as arguments.
  * **Note**: Test each program to make sure it's been successfully restricted before using.

## Examples ##

* `cjdnsify lynx [fc13:6176:aaca:8c7f:9f55:924f:26b3:4b14]:82`
* `cjdnsify wget http://[fc13:6176:aaca:8c7f:9f55:924f:26b3:4b14]:82/testdownload.txt`

## Programs ##

The lists below are a small sample of programs I've tested and the results I got. That said, other versions of the same program might have different results, and it seems possible that build flags and patches used by different distributions might have an affect on the results as well (I tested using packages build by **Arch Linux**).

### Working ###

* **chromium** v35.0.1916.153
* **curl** v7.37.0
* **firefox** v30.0
* **hexchat** v2.10.0
* **links** v2.8
* **lynx** v2.8.8
* **wget** v1.15

### Not Working ###

* **host** (from **dnsutils** 9.9.2.P2)
* **ping** (from **iputils** v20121221)

## CREDITS ##

Written by Kevin MacMartin: [GitHub Projects](https://github.com/prurigro?tab=repositories) | [Arch Linux AUR Packages](https://aur.archlinux.org/packages/?SeB=m&K=prurigro)

## LICENSE ##

This script is open source and licensed under the [GPLv3](http://www.gnu.org/copyleft/gpl.html).
