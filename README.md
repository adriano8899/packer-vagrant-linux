[Packer](http://packer.io) templates for Linux boxes.

- [x] CentOS 6.9 (Minimal) 64-bit
- [ ] CentOS 7 (Minimal) 64-bit - todo
- [x] Ubuntu 12.04 LTS (Precise Pangolin) 64-bit
- [x] Ubuntu 14.04 LTS (Trusty Tahr)  64-bit
- [ ] Ubuntu 16.04 LTS (Xenial Xerus)  64-bit - todo

Use the box (generated in `build` subdirectory) with
[Vagrant](http://vagrantup.com) and [VirtualBox](http://virtualbox.org).

# Quick Guide
## Setup
---
#### Linux
virtualbox, vagrant, virtualenv is are required, this can also be installed using the `ifs` example below:

* Set-up Environment
```bash
git clone repo
virtualenv .
source bin/activate
pip install -r pip_requirements.txt
```
* Search and Check for packer (or other packages)

`ifs grep packer`
 or
 `ifs ls | grep "virtualbox"`

 ```bash
ifs info packer
      default_version: 0.11.0
      dependencies: unzip
      description: packer
      download_url: https://releases.hashicorp.com/packer/VERSION/packer_VERSION_linux_amd64.zip
      current_version: Not Installed
```
* Install packer using [`ifs`](https://github.com/cbednarski/ifs-python)
```bash
ifs install packer
```
---
#### MAC

* Install packer using homebrew
```bash
brew install packer
```
---

## Build
* Build virtualbox .box image
```bash
packer build centos-6.9-x86_64.json
packer build ubuntu-12.04-amd64.json
packer build ubuntu-14.04-amd64.json
```
***Tip -***
Remove the output-virtualbox-iso before running each build (if it exists): `rm -rf output-virtualbox-iso/`
