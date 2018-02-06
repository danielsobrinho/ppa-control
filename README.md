# ppa-control

PPA Add and Remove Repositorys

Substitute ppa-purge at Debian and your childs.

Only automates 'add-apt-repository' and 'add-apt-repository --remove':.

For install use the bellow commands:

# Create the file:

sudo nano /usr/local/bin/ppa-control

# Content the file:
====================================

#!/bin/bash

action=$1
ppa=$2

if [ -z $ppa ]; then
        echo "PPA not defined"
        exit
fi

if [ $action = 'add' ]; then
        sudo add-apt-repository $ppa
        #echo ""
elif [ $action = 'remove' ]; then
        sudo add-apt-repository --remove $ppa
        #echo ""
else
        echo "Action not defined."
fi


# Authorize the file for execution:

sudo chmod +x /usr/local/bin/ppa-control
 
