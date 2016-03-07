# sec-tools [![Build Status](https://travis-ci.org/eugenekolo/sec-tools.svg?branch=master)](https://travis-ci.org/eugenekolo/sec-tools)

Curated collection of tools for security research, CTFs, and fun, that I enjoy. Similar to zardus's ctf-tools, but with a more general focus on security.

Installers for the following tools are included:

| Category | Tool | Description |
|----------|------|-------------|
| binary | [apktool](https://ibotpeaches.github.io/Apktool/) | Dissect, dis-assemble, and re-pack Android APKs | <!--test-->
| binary | [binwalk](https://github.com/devttys0/binwalk.git) | Firmware (and arbitrary file) analysis tool. | <!--test-->
| binary | [checksec](https://github.com/slimm609/checksec.sh) | Check binary hardening settings. | <!--test-->
| binary | [hxd](https://mh-nexus.de/en/hxd/) | A simple hex editor. Ran through `wine`. Uses wine. | <!--uses-wine-->
| binary | [idafree](https://www.hex-rays.com/products/ida/support/download_freeware.shtml) | The most popular interactive disassembler, free edition. Uses wine. | <!--uses-wine-->
| binary | [jdgui](http://jd.benow.ca/) | A graphical Java Decompiler. Uses wine. | <!--uses-wine-->
| binary | [peda](https://github.com/longld/peda) | Enhanced environment for gdb. | <!--test-->
| binary | [preeny](https://github.com/zardus/preeny) | A collection of helpful preloads (compiled for many architectures!). | <!--test-->
| binary | [qemu](http://qemu.org) | Latest version of qemu! | <!--test-->
| binary | [qira](http://qira.me) | Parallel, timeless debugger. | <!--test-->
| binary | [radare2](http://www.radare.org/) | Some crazy thing crowell likes. | <!--test-->
| binary | [ropgadget](https://github.com/JonathanSalwan/ROPgadget) | This tool lets you search your gadgets on your binaries to facilitate your ROP exploitation. | <!--test-->
| binary | [upx](http://upx.sourceforge.net/) | A free and popular packer/unpacker. | <!--test-->
| crypto | [aeskeyfind](https://citp.princeton.edu/research/memory/code/) | Find AES keys in a memory dump | <!--test-->
| crypto | [cribdrag](https://github.com/SpiderLabs/cribdrag) | Interactive crib dragging tool (for crypto). | <!--test-->
| crypto | [evilize](http://www.mathstat.dal.ca/~selinger/md5collision/) | Tool to create MD5 colliding binaries | <!--test-->
| crypto | [foresight](https://github.com/ALSchwalm/foresight) | A tool for predicting the output of random number generators. To run, launch "foresee". | <!--test-->
| crypto | [hashid](https://code.google.com/p/hash-identifier/source/checkout) | Simple hash algorithm identifier. | <!--test-->
| crypto | [msieve](https://sourceforge.net/projects/msieve/) | Factor primes, such as for RSA. | <!--test-->
| crypto | [pkcrack](https://www.unix-ag.uni-kl.de/~conrad/krypto/pkcrack.html) | PkZip encryption cracker. | <!--test-->
| crypto | [padbuster](https://github.com/GDSSecurity/PadBuster) | Automated script for performing Padding Oracle attacks | <!--test-->
| crypto | [python-paddingoracle](https://github.com/mwielgoszewski/python-paddingoracle) | Padding oracle attack automation. | <!--test-->
| crypto | [ssh_decoder](https://github.com/jjyg/ssh_decoder) | A tool for decoding ssh traffic. | <!--test-->
| crypto | [xortool](https://github.com/hellman/xortool) | XOR analysis tool. | <!--test-->
| fuzzers | [afl](http://lcamtuf.coredump.cx/afl/) | State-of-the-art fuzzer. | <!--test-->
| fuzzers | [taintgrind](https://github.com/wmkhoo/taintgrind) | A valgrind taint analysis tool. | <!--test-->
| stego | [ElectronicColoringBook](https://doegox.github.io/ElectronicColoringBook/) | Colorize data file according to repetitive chunks. | <!--test-->
| stego | [lsbsteg](https://github.com/RobinDavid/LSB-Steganography) | stego files into images using the Least Significant Bit. | <!--test-->
| stego | [poppler](http://poppler.freedesktop.org/) | A suite of tools to help take apart and work with PDF files | <!--test-->
| stego | [steganabara](http://www.caesum.com/handbook/stego.htm) | Another image steganography solver. | <!--test-->
| stego | [stegdetect](http://www.outguess.org/) | Steganography detection/breaking tool. | <!--test-->
| stego | [stegsolve](http://www.caesum.com/handbook/stego.htm) | Image steganography solver. | <!--test-->
| tools | [bruteforce](http://github.com/eugenekolo/sec-tools) | A simple starter script for bruteforcing | <!--test-->
| tools | [entropy](http://github.com/eugenekolo/sec-tools) | A simple tool to test entropy of a file | <!--test-->
| tools | [extundelete](http://extundelete.sourceforge.net/) | Recover deleted files from an ext3 or ext4 partition. | <!--test-->
| tools | [pyunpack](https://github.com/kholia/exetractor-clone) | Unpacker for packed Python executables | <!--test-->
| tools | [shoe](http://github.com/eugenekolo/sec-tools) | A simple tool to assist with TCP remote communication | <!--test-->
| tools | [wordlist](https://github.com/eugenekolo/win-sec-tools/releases/download/v1.0/wordlist.txt.gz) | A huge wordlist to use for cracking or whatever. | <!--test-->
| web | [burpsuite](http://portswigger.net/burp) | Web proxy to do naughty web stuff. | <!--test-->
| web | [dirs3arch](https://github.com/maurosoria/dirs3arch) | Web path scanner. | <!--test-->
| web | [mitmproxy](http://mitmproxy.org/) | A programmable and interactive HTTP proxy useful | <!--test-->
| web | [net-creds](https://github.com/DanMcInerney/net-creds) | Sniffs sensitive data from interface or pcap | <!--test-->
| web | [sqlmap](http://sqlmap.org/) | SQL injection automation engine. | <!--test-->

## Usage
To use, do:

```bash
# set up the path
./sec-tools setup

# list the available category/tools
sec-tools list

# install whatever <category/tool-name>
sec-tools install binary/radare2

# use the tool - your path is automatically configured
rabin2 -e /bin/ls
```

The tools attempt to download and install themselves in their desiginated self-contained directory.
The binaries of each tool are soft linked into /path/to/sec-tools/bin which is added to your path when you run `manage-tools setup`

## Adding Tools
To add a tool (say, named *toolname*), do the following:

1. Decide what category it falls under. You probably shouldn't create a new one.
2. Create a `category\toolname` directory.
3. Create an `install-ctf.sh` script.

### Install Scripts
The install script will be run with `$PWD` being `toolname`. It should install the tool into this directory, in as contained a manner as possible.
Ideally, full uninstallation should be possible with a `git clean`.

The install script should create a `bin` directory and put its executables there.
These executables will be automatically linked into the main `bin` directory for the repo.
They could be launched from any directory, so don't make assumptions about the location of `$0`!

## License
The individual tools are all licensed under their own licenses.
As for sec-tools itself, it is "starware".
If you find it useful, star it on github (https://github.com/eugenekolo/sec-tools).

## Acknowledgements
Built upon [ctf-tools](github.zom/zardus/ctf-tools). Be sure to check them out.
