# Deploying the role

Initial preparation consists of installing Ansible and
dependent modules (probably into a Python virtual environment).

    $ pip install -r requirements.txt
    $ ansible-galaxy install -r requirements.yml

>   You probably need a VM like [VirualBox] (tested with v6.0.8) for
    MiniKube that supports Kubernetes 1.16 or better.
    This role has been tested using Minikube v1.6.2 and Kubernetes v1.16.4.

Ensure [Minikube] is running...

    $ minikube start --cpus 4 --memory 8192 --disk-size 40g \
        --kubernetes-version v1.16.4 \
        --vm-driver virtualbox

and then to deploy via the ansible playbook (where you may need
to provide the location of your Python installation)...

    $ ansible-playbook site.yml -e ansible_python_interpreter=??? \
        -e letsencrypt_email=anyone@example.com

and un-deploy...

    $ ansible-playbook site.yml  -e ansible_python_interpreter=??? \
        -e state=absent

---

[minikube]: https://kubernetes.io/docs/tutorials/hello-minikube
[virtualbox]: https://www.virtualbox.org
