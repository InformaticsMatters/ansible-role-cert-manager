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

    # Email address used for ACME registration
    letsencrypt_email: SetMe
    
Dependencies
------------

-   (none)

Example Playbook
----------------

**NOTE** The example below assumes that you have a running Kubernetes
cluster.

    - hosts: servers
      tasks:
      - include_role:
          name: informaticsmatters.cert-manager
        vars:
          letsencrypt_email: anyone@example.com

License
-------

Apache 2.0 License

Author Information
------------------

alanbchristie
