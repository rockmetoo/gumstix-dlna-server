## Overview

How to make a personal dlna stream server using gumstix overo.

## Hardware Requirements

    Gumstix overo
    Gumstix chestnut43 board

## Software Requirements

    Host os: Ubuntu
    Gumstix os: Yocto linux

## Enough Talk Let's Open a Terminal

**1.  Install repo tool**

Download the Repo script:

    $ curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > repo

Make it executable:

    $ chmod a+x repo

Move it on to your system path:

    $ sudo mv repo /usr/local/bin/

**2.  Get the yocto-linux repository**

    $ mkdir yoctoLinux
    $ cd yoctoLinux
    
Get the stable version:

    $ repo init -u git://github.com/gumstix/Gumstix-YoctoProject-Repo.git -b master
    $ repo sync
    
More Coming soon....

## Useful links

[Visit overo](https://store.gumstix.com/index.php/category/33/)

[Visit chestnut43](https://store.gumstix.com/index.php/products/237/)
