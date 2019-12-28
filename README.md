Ansible Role - informaticsmatters.cert-manager
==============================================

A Role for the installation of the cert-manager application into a Kubernetes
cluster.

Requirements
------------

-   Kubernetes

Role Variables
--------------

    # To uninstall from the cluster
    # state: absent
    state: present
    
Dependencies
------------

-   (none)

Example Playbook
----------------

**NOTE** The example below assumes that you have a running Kubernetes|OpenShift
cluster and that you have sufficient permissions in the `pysimple` namespace.

    - hosts: servers
      tasks:
      - include_role:
          name: informaticsmatters.cert-manager

License
-------

Apache 2.0 License

Author Information
------------------

alanbchristie
