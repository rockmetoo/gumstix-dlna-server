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
    
Get the stable linux version:

    $ repo init -u git://github.com/gumstix/Gumstix-YoctoProject-Repo.git -b master
    $ repo sync

**3.  Initialize the build environment**

    $ export TEMPLATECONF=meta-gumstix-extras/conf 
    $ source ./poky/oe-init-build-env
    
**4.  Build a console image**

    $ bitbake gumstix-console-image

Go for a cool dinner or sleep. It may take some couple of hours depending on your network connection:relaxed:

**5. Create a bootable micro SD card**

    $ cd poky/meta-gumstix-extras/scripts
    $ sudo ./mk2partsd <block device>
    
If you get an error, make sure your operating system has not automatically mounted 
the drives. Once this is successful, go ahead and mount both the drives. 

**6. Write your yocto image**

    $ cd build/tmp/deploy/images/{overo|duovero|pepper}   
    
Write the bootloader, kernel and the root file system into your card:

    $ cp MLO u-boot.img uImage /media/boot 
    $ sudo tar xaf gumstix-console-image.tar.bz2 -C /media/rootfs --strip-components=1

And you should make sure all the files are written:

    $ sync

**7. Bootup gumstix overo**

    $ nand erase 240000 20000

More Coming soon....

## Useful links

[Visit overo](https://store.gumstix.com/index.php/category/33/)

[Visit chestnut43](https://store.gumstix.com/index.php/products/237/)

[Visit Yocto](https://github.com/gumstix/Gumstix-YoctoProject-Repo)
