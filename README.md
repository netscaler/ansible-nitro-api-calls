# Ansible NITRO API calls

This repository contains sample playbooks that make NITRO API calls
using standard Ansible modules.

Each playbook contains only one or two tasks. For more complete workflows tasks
should be combined in a more complete playbook. Such examples can be
found under the examples directory.


## Playbook listing

In the following sections we detail the function of each playbook.

All playbooks require to be run with the `delegate_to: localhost` option
since we do not want Ansible to connect to Netscaler directly but instead
run the NITRO API calls from localhost addressed to the Netscaler NSIP.

There is a number of variables that each playbook uses. These are
defined withing each playbook.

The exception is the NITRO API credentials variables which are defined
in the inventory file. These variables ( `{{ nsip }}`, `{{ nitro_user }}`,
`{{ nitro_pass }}` ) are needed in all playbooks.

Following are the details of each playbook.

### ns\_file\_delete.yaml

Deletes a file on Netscaler.

Variables used:

* filelocation: path of the file on Netscaler
* filename: name of the file on Netscaler

### ns\_file\_get.yaml

Retrieve a file from Netscaler.

Variables used:

* filelocation: path of the file on Netscaler.
* filename: name of the file on Netscaler.
* localfile: absolute path of the target saved local file.

### ns\_file\_put.yaml

Upload a file to Netscaler.

Variables used:

* filelocation: path of the file on Netscaler.
* filename: name of the file on Netscaler.
* localfile: absolute path of the source local file.


### ns\_reboot.yaml

Reboot Netscaler.

Note that this NITRO API call does not work with CPX.
You will need to use docker commands to restart the CPX container.

Variables:

* warm\_reboot: boolean value to do a warm reboot.
 
### resource\_add.yaml

Add a configuration resource to Netscaler.

Variables:

* resource: path of the resource.
* request\_payload: request JSON content.

Refer to NITRO reference documentation for variable values explanation.

### resource\_delete.yaml

Delete a configuration resource on Netscaler.

Variables:

* resource: path of the resource.

Refer to NITRO reference documentation for variable values explanation.

### resource\_disable.yaml

Disable a configuration resource on Netscaler.

Variables:

* resource: path of the resource.
* request\_payload: request JSON content.

Refer to NITRO reference documentation for variable values explanation.

### resource\_enable.yaml

Enable a configuration resource on Netscaler.

Variables:

* resource: path of the resource.
* request\_payload: request JSON content.

Refer to NITRO reference documentation for variable values explanation.

### resource\_get.yaml

Get details of a single configuration resource.

Variables:

* resource: path of the resource.

The returned data is under the `json` key in the playbook return value.


### resource\_get\_all.yaml

Get details of all resources of one kind.

Variables:

* resource: path of the resource.

The returned data is under the `json` key in the playbook return value.

### resource\_get\_attrs.yaml

Get specific attributes of a configuration resource.

Variables:

* resource: path of the resource.
* attrs: list of attributes to retrieve.

The returned data is under the `json` key in the playbook return value.

### resource\_update.yaml

Update the attributes of an existing resource.

* resource: path of the resource.
* request\_payload: request JSON content.


### ns\_save\_running\_config.yaml

Save Netscaler's running configuration.


### ns\_feature

Enable / Disable Netscaler feature.

Variables:

* feature\_action: determine the action to be performed. Valid values are `enable`, `disable`.
* request\_payload: request JSON content.
