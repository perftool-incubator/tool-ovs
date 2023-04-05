# ovs
Scripts to help collect and post-process Open vSwitch (OVS) and Open Virtual Network (OVN).

## Scripts

Name | Description
-----|------------
ovs-collect | Collects data at a specified interval on Open vSwitch bridges and flows, then saves the output to separate files named after the command being run.
ovs-post-process | Perform post-processing tasks on Open vSwitch data, such as generating datapath statistics or dumping flow tables. Saves output to compressed files that adhere to a [Common Data Model (CDM) Schema](https://github.com/perftool-incubator/CommonDataModel). 
ovs-start | Sets the standard output and error to a file, collects some system information, parses command line arguments, and executes the ovs-collect command with a specified interval.
ovs-stop | Writes output to a file, identifies the PID of a running process (ovs-collect) using a file, and then sends it a SIGTERM signal to stop it. If the [xz utility](https://tukaani.org/xz/) is available, it compresses any ovs data files.


## JSON files

Name | Description
-----|------------
rickshaw.json | Defines a configuration for ovs tool used for collecting data. The file specifies which scripts should be run on the controller and collector, as well as whitelisted and blacklisted endpoints and their corresponding collector types.
workshop.json | Describes a workshop environment, including user requirements and installation instructions. In this case, the only requirement is for the OVS source code, which is downloaded from a specified URL and compiled.
