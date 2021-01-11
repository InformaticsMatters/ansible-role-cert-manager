Ansible Role - informaticsmatters.cert_manager
==============================================

![lint](https://github.com/InformaticsMatters/ansible-role-cert-manager/workflows/lint/badge.svg)

![GitHub release (latest by date)](https://img.shields.io/github/v/release/informaticsmatters/ansible-role-cert-manager)
![Ansible Role](https://img.shields.io/ansible/role/45879)

A Role for the installation of the cert-manager application into a Kubernetes
cluster.

Requirements
------------

-   Kubernetes

Role Variables
--------------

    # To uninstall from the cluster
    # state: absent
    cm_state: present
    # The period of time (seconds) to wait for the cert-manager
    # to get to the desired state. It may take several minutes for
    # container initialisation, a period of more than 3 minutes
    # is recommended.
    cm_wait_timeout: 360

    # Email address used for ACME registration
    cm_letsencrypt_email: SetMe
    
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
          name: informaticsmatters.cert_manager
        vars:
          cm_letsencrypt_email: anyone@example.com
          cm_wait_timeout: 600

License
-------

Apache 2.0 License

Author Information
------------------

alanbchristie
