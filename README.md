# GANSO environment installer

This script automates the installation, setting up and starting/stopping of the packages and programs required to run the [GANSO (GST And Network Slice Operator)](https://github.com/josetakeru/GANSO) **environment** (*note: you will still need to install python3 and the required modules to run GANSO itself*).

## Usage

GANSO leverages on the *[mininet](http://mininet.org/download/)* and *[ONOS](https://opennetworking.org/onos/)* tools to create virtual networks and their SDN controllers respectively. These may be run on a different host or VM than that on which GANSO will be executed as long as all machines are able to talk to each other.

Running the script by itself will start both mininet and ONOS and stop them upon exiting *mininet* (*note: you need sudo priviledges to run the script since it installs packages and manages mininet*).

    sudo ./setup_GANSO_environment.sh

The script allows setting different *OPTIONS* that will be enforced before starting *mininet* and *ONOS*:
 * *-p*: Install required packages.
 * *-o*: Install *ONOS* version 2.3.0.
 * *-v ONOS_VERSION*: Install *ONOS_VERSION* version.
 * *-m*: Install *mininet*.
 * *-t PATH/TO/CUSTOM_TOPO*: - Use custom mininet topology (requires option "-n"!) e.g. -t ./custom_topo.py -n customTopo.
 * *-n TOPO_NAME*: Set name of the custom topo (requires option "-t"!) e.g. -t ./custom_topo.py -n customTopo
 * *-h*: Show usage.

For example, to install *ONOS* version 2.4.0 and start *mininet* with a custom topology found in */foo/bar* with name *custom_topo*:

    sudo ./setup_GANSO_environment.sh -v 2.4.0 -t /foo/bar/custom_topo.py -n custom_topo