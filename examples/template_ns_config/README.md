# Templating configuration

This example uses the template module to output a valid ns.conf,
uploads it to Netscaler and then reboots Netscaler for the configuration
changes to take effect.

The general workflow of the playbook is the following.

1. Produce ns.conf from Jinja2 template file
2. Delete the old ns.conf on NetScaler.
3. Upload new ns.conf
4. Reboot NetScaler to apply the changes to ns.conf.

A more detailed overview can be found here
http://netscaler-ansible.readthedocs.io/en/latest/generic\_modules/template\_ns\_conf.html
