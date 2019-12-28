# Deploying the role

Initial preparation consists of installing Ansible and
dependent modules (probably into a Python virtual environment).

    $ pip install -r requirements.txt
    $ ansible-galaxy install -r requirements.yml

>   You probably need a VM like [VirualBox] (tested with v6.0.8) for
    MiniKube and MiniShift.

## Deploying to MiniKube

Ensure [Minikube] is running...

    $ minikube start --cpus 4 --memory 8192 --disk-size 40g \
        --kubernetes-version v1.15.0 \
        --vm-driver virtualbox
    $ kubectl create -f namespace.yaml
    $ kubectl config set-context --current --namespace=pysimple

>   Tested using Minikube v1.2.0 and Kubernetes v1.15.0

and then to deploy via the ansible playbook (where you may need
to provide the location of your Python installation)...

    $ ansible-playbook site.yml -e ansible_python_interpreter=???

and un-deploy...

    $ ansible-playbook site.yml  -e ansible_python_interpreter=??? \
        -e state=absent

---

[minikube]: https://kubernetes.io/docs/tutorials/hello-minikube
[virtualbox]: https://www.virtualbox.org
