---
title: "OpenShift"
metaTitle: "OpenShift is the meta title tag for this page"
metaDescription: "This is the meta description for this page"
---

### XPLAT

- [**OpenShift Online](https://manage.openshift.com/sign_in) (**hieptk@fpt.com.vn** / *****)
- [**Access URL**](https://okdconsole.xplat.fpt.com.vn:8443/) (**fti-hieptk** / Dong*@)
- [**Documentation**](https://docs.xplat.fpt.com.vn/documentation/#deploy-application-on-xplat)
- [**Gitlab**](https://gitlab.xplat.fpt.com.vn/users/sign_in)
- Modify: **/etc/docker/daemon.json**

``` json
{
    "insecure-registries" : ["docker-registry-default.paas.xplat.fpt.com.vn"]
}
```

```bash
docker login --username=fti-hieptk --password=<token> docker-registry-default
.paas.xplat.fpt.com.vn
com.vn
docker tag ubuntu:20.04 docker-registry-default.paas.xplat.fpt.com.vn/fptai-stag/ubuntu:20.04
docker push docker-registry-default.paas.xplat.fpt.com.vn/fptai-stag/ubuntu:20.04

oc whoami
oc status
oc status --suggest
oc project
oc new-project <project-name>
oc get pods -w
oc get builds
oc start-build nodejs-ex --follow
oc get all: List all components in a project
oc describe secret deployer-token-7kmxf -n fptai-stag
oc describe secret deployer-token-fwqc7 -n fptai-stag
oc create sa <service_account_name>
# secret: deployer-token-fwqc7 (sa: deployer)
oc policy add-role-to-user edit system:serviceaccount:fptai-stag:deployer
oc login --token=eyJhbGciOiJSUzI1NiIsImtpZCI6IiJ9.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJmcHRhaS1zdGFnIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6ImRlcGxveWVyLXRva2VuLWZ3cWM3Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQubmFtZSI6ImRlcGxveWVyIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQudWlkIjoiNzQ3YjJjYWYtY2EyZi0xMWVhLTgyNzktMDA1MDU2OTA5MDczIiwic3ViIjoic3lzdGVtOnNlcnZpY2VhY2NvdW50OmZwdGFpLXN0YWc6ZGVwbG95ZXIifQ.Sp-StKPdrNndwt8tsl0i9uooT9lneKX4RwsNn0ggmG7MW2KVkBnh7osdv_SGGjdSBEXuAdvjWMYnikuR-Lx7Hd98Yp__T283W_zbVh8_k68CPqkjYUG4J9mNzO2rQVcfE5aLm6b3Tq94hHYdoJwNakouE0LF7m65gNRV_5g6BTr3uNizBndI4NezRxhBybyVBESmKUSKHGyVyjZMrzShHrZxzqUpiK7znz2MP6hWFVdQIyGvsEHCJ_O0Lx3hPkBDfeuDTcNN6CVDUOnSFgzUw3XnOaSoC0jGcSCnM3UEIXylKF-OoKKyPCDat6VSbZlcw68195EG37LS_ZNt5wpM5w

##
oc project <project_name>
oc adm policy add-role-to-user <role_name> <username>
<role_name> can be: `admin`, `edit`, `view`
oc get rolebindings
```

### MINISHIFT

[**Official**](https://www.okd.io/minishift/)

[**Official Setup guide**](https://docs.okd.io/3.11/minishift/getting-started/setting-up-virtualization-environment.html)

[**Another Guide**](https://computingforgeeks.com/how-to-run-local-openshift-cluster-with-minishift/)

#### Install KVM

- <https://www.tecmint.com/install-kvm-on-ubuntu/>
- <https://linuxconfig.org/install-and-set-up-kvm-on-ubuntu-20-04-focal-fossa-linux>

#### Commands

```bash
minishift start
minishift stop
minishift status
minishift delete
minishift start --vm-driver virtualbox
minishift config set vm-driver virtualbox
minishift config set vm-driver kvm
## Information
https://console-openshift-console.apps.us-west-1.starter.openshift-online.com/command-line-tools
```

### [OpenShift Products](https://www.openshift.com/products)

- **OpenShift** is a family of containerization software developed by Red Hat. Its **_flagship_** product is the **OpenShift Container Platform**—an on-premises platform as a service built around Docker containers orchestrated and managed by Kubernetes on a foundation of Red Hat Enterprise Linux.
  - **Latest version**: [OpenShift 4.5](https://www.openshift.com/blog/openshift-4.5-arrives-bringing-new-supported-installations)
  - [**Documentation**](https://docs.openshift.com/container-platform/4.5/welcome/index.html)

- [**OKD**](https://www.okd.io/), known until August 2018 as OpenShift Origin (Origin Community Distribution) is the upstream community project used in OpenShift Online, OpenShift Dedicated, and OpenShift Container Platform.
  - [**Release**](https://github.com/openshift/okd/releases)
  - [**Documentation**](https://docs.okd.io/latest/welcome/index.html)
  - [**Download**](https://www.okd.io/download.html)

- [**OpenShift Online (RHOO)**](https://www.openshift.com/products/online/) is Red Hat's public cloud application development (public PaaS) and hosting service which runs on AWS and IBM Cloud.

- **Other Products**

| Product                           | Description                         |
|-------------------------------|-----------------------------------|
| Red Hat OpenShift Dedicated | Private, high-availability Red Hat OpenShift clusters hosted on Amazon Web Services and Google Cloud |
| Microsoft Azure Red Hat OpenShift | Fully managed Red Hat OpenShift service on Microsoft Azure |
| Red Hat OpenShift on IBM Cloud | Fast and secure way to containerize and deploy enterprise workloads in Kubernetes clusters |
| Red Hat OpenShift Container Platform (formerly known as OpenShift Enterprise) | Build, deploy and manage your applications across cloud- and on-premise infrastructure |
| Amazon Red Hat OpenShift | Fully managed Red Hat OpenShift service deployed and operated on AWS |

- [**oc**](https://downloads-openshift-console.apps.us-west-1.starter.openshift-online.com/amd64/linux/oc.tar): OpenShift Command Line Interface (CLI), the oc binary offers the same capabilities as the kubectl binary, but it is further extended to natively support OpenShift Container Platform features.

- [**odo**](https://github.com/openshift/odo): Developer-focused CLI for OpenShift

- [**Learn OpenShift**](https://learn.openshift.com/)

- [**Katacoda OpenShift**](https://www.katacoda.com/openshift)

- [**Blog OpenShift**](https://www.openshift.com/blog)

- [**OpenShift Installer**](https://github.com/openshift/installer)

- **Ansible and OpenShift**
  - [**Ansible Install and Configure OpenShift**](https://docs.ansible.com/ansible-container/openshift/index.html)
  - [**Containerized openshift-ansible**](https://hub.docker.com/r/openshift/origin-ansible)
  - [**Github OpenShift-Ansible**](https://github.com/openshift/openshift-ansible)
  - [**ansible-ansible-openshift-ansible What? Why?**](https://pagure.io/ansible-ansible-openshift-ansible)

### NOTES

- [**Kubernetes Ingress vs OpenShift Route**](https://www.openshift.com/blog/kubernetes-ingress-vs-openshift-route)
- [**Catridge vs Image**](https://docs.openshift.com/enterprise/3.0/whats_new/carts_vs_images.html)
- Setting the runAsUser to an ID within the range 1000000000, 1000009999.
- OpenShift also offers on-premises version known as OpenShift Enterprise. In OpenShift, developers have the leverage to design scalable and non-scalable applications and these designs are implemented using HAproxy servers.
- akin to: very similar to something

### REFERENCES

- <https://b-ok.asia/s/openshift> (**DOWNLOAD EBOOKS**)
- <https://www.tutorialspoint.com/openshift/index.htm> (**TUTORIALS**)

### TODO

```TODO
Login OpenShift Online: https://manage.openshift.com/

https://console-openshift-console.apps.us-west-1.starter.openshift-online.com/api-explorer

OpenShift:
  - Login
  - Download oc
  - Copy Login Command
  - Login using login command ==> This only valid for 1 day ==> Create Service Account to run with Ansible ma` ko phai login (do login thi` phai copy login command ma copy login command thi phai vao duoc UI, ma vao duoc UI thi phai dung Authenticator)
  - Use Registry:
    Modify /etc/docker/daemon.json
    docker tag ubuntu:20.04 docker-registry-default.paas.xplat.fpt.com.vn/fptai-stag/ubuntu:20.04
    docker push docker-registry-default.paas.xplat.fpt.com.vn/fptai-stag/ubuntu:20.04


  - Co the Deploy tu GitLab cua xPlat nhung phai la nguoi cua FIS hay the nao day



  - s2i: S2I generates a new Docker image using SOURCE CODE and a BUILDER DOCKER IMAGE (take application source code as an input and produce a new image that runs the assembled application as output). Giong' dung` gcloud builder
    Commonly used Docker builder images: Python, Ruby, Perl, Node.JS etc.

    https://github.com/openshift/source-to-image

    Download s2i: https://github.com/openshift/source-to-image/releases/latest

    $ s2i build https://github.com/sclorg/django-ex centos/python-35-centos7 hello-python
    $ docker run -p 8080:8080 hello-python

    $ s2i build https://github.com/openshift/ruby-hello-world centos/ruby-25-centos7 test-ruby-app
    $ docker run --rm -i -p :8080 -t test-ruby-app

    https://github.com/openshift/source-to-image/blob/master/examples/nginx-centos7/README.md



Lession 1:
  oc login --
  oc whoami
  oc status
  oc project
  oc new-project test-project
  oc get project
  oc project fptai-stag

Lession 2:





oc get pods -w
oc get builds
oc start-build nodejs-ex --follow
oc get all: List all components in a project
oc describe secret deployer-token-7kmxf -n fptai-stag
oc describe secret deployer-token-fwqc7 -n fptai-stag
oc create sa <service_account_name>
# secret: deployer-token-fwqc7 (sa: deployer)
oc policy add-role-to-user edit system:serviceaccount:fptai-stag:deployer
oc login --token=eyJhbGciOiJSUzI1NiIsImtpZCI6IiJ9.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJmcHRhaS1zdGFnIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6ImRlcGxveWVyLXRva2VuLWZ3cWM3Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQubmFtZSI6ImRlcGxveWVyIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQudWlkIjoiNzQ3YjJjYWYtY2EyZi0xMWVhLTgyNzktMDA1MDU2OTA5MDczIiwic3ViIjoic3lzdGVtOnNlcnZpY2VhY2NvdW50OmZwdGFpLXN0YWc6ZGVwbG95ZXIifQ.Sp-StKPdrNndwt8tsl0i9uooT9lneKX4RwsNn0ggmG7MW2KVkBnh7osdv_SGGjdSBEXuAdvjWMYnikuR-Lx7Hd98Yp__T283W_zbVh8_k68CPqkjYUG4J9mNzO2rQVcfE5aLm6b3Tq94hHYdoJwNakouE0LF7m65gNRV_5g6BTr3uNizBndI4NezRxhBybyVBESmKUSKHGyVyjZMrzShHrZxzqUpiK7znz2MP6hWFVdQIyGvsEHCJ_O0Lx3hPkBDfeuDTcNN6CVDUOnSFgzUw3XnOaSoC0jGcSCnM3UEIXylKF-OoKKyPCDat6VSbZlcw68195EG37LS_ZNt5wpM5w

##
oc project <project_name>
oc adm policy add-role-to-user <role_name> <username>
<role_name> can be: `admin`, `edit`, `view`
oc get rolebindings

OpenShift CLI (oc)

s2i:
Dowload tools: https://github.com/openshift/source-to-image/releases/latest


$ s2i build https://github.com/sclorg/django-ex centos/python-36-centos7 hello-python
$ docker run -p 8080:8080 hello-python

https://github.com/sclorg/s2i-python-container/blob/master/3.6/Dockerfile (centos/python-36-centos7)
https://github.com/sclorg/s2i-base-container/blob/master/base/Dockerfile (centos/s2i-base-centos7)
https://github.com/sclorg/s2i-base-container/blob/master/core/Dockerfile (centos/s2i-core-centos7)
Core: From centos:7


GOLANG:
  https://github.com/sclorg/golang-container/tree/master/1.12

  1 login

Copy login command

Create sa account 
Set role
Create a i dont have the name
Create s route

Catridge? 
Oc create a project 

Oc create app

Ascinema qua trinh install kvm or virtualbox openshift

build 1 cai centos... s2i chua dockerfile...

```