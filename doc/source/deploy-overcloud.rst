Deploying the Overcloud
=======================

All the commands on this page require that the appropriate stackrc file has
been sourced into the environment::

    source stackrc

Registering Nodes
-----------------

Register nodes for your deployment with Ironic::

    instack-ironic-deployment --nodes-json instackenv.json --register-nodes

Discovering Nodes
-----------------

Discover hardware attributes of nodes and match them to a deployment profile::

    instack-ironic-deployment --discover-nodes

Check what profiles were matched for the discovered nodes::

    instack-ironic-deployment --show-profile

Deploying Nodes
---------------

Create the necessary flavors::

    instack-ironic-deployment --setup-flavors

Deploy the the *openstack-full* image to 3 nodes::

    COMPUTE_COUNT=3 CONTROL_COUNT=0 instack-ironic-deployment --deploy-nodes
