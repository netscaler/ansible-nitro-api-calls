This example shows how to configure a NetScaler instance
by sending the NITRO API calls through MAS.

We utilize the tasks from the playbooks under the `playbooks/mas`
folder.

The play is similar to the direct nitro api call example.

We essentially create or update a resource and then delete it,
to test the a range of possible NITRO operations.

Refer to the toplevel README to see how the playbook differs
from the direct NITRO API calls to NetScaler.
