eucalyptus-register
===================

Register all the Eucalyptus cloud components all together

** *WARNING !!!* **
*This role has to be used in the deployment of Eucalyptus cloud !*

Requirements
------------

hosts:

- clc | Cloud Controller
- ufs | User Facing Services
- cc | Cluster Controllers
- sc | Storage Controllers
- nc | Node Controllers
- walrus | S3 builtin-backend


Role Variables
--------------

This variable MUST NOT BE CHANGED if you are not an Eucalyptus engineer

| Name | Default | Description | Note
|--- |--- |--- |---
| cpu_overcommit | 1 | Defines the factor of overcommitting for Compute nodes | None
| networking_mode | None | Eucalyptus networking mode | Must be the same for all roles
| use_vlans| true | Eucalyptus using VLANs for instances traffic | None


Dependencies
------------

- JohnPreston.eucalyptus-initialize

** *WARNING !!!* **
- * These roles are not in the meta dependencies, therefore they wont be downloaded and installed. *

Example Playbook
----------------

```

- hosts:
  - clc
  - cc
  roles:
  - JohnPreston.eucalyptus-register
  vars:
  - networking_mode : EDGE
  - use_vlans: true

```

License
-------

Apache

Author Information
------------------

John Preston [John Mille]
