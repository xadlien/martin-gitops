# martin-gitops
## Description
This is a Github repository to deploy applications to kubernetes clusters I manage using flux gitops. This is a current work-in-progress though most current code works fully and is complete.  
## Repository Structure
### `apps`
This directory houses kubernetes definitions for applications unrelated to backend support. Examples are my git server or website. Adding another app in requires only a folder under `apps` and then the related kubernetes manifests. 
### `infrastructure`
This directory houses kubernetes definitions for applications related to backend support. Examples are cert-manager and external-dns. Adding another infrastructure app in requires only a folder under `infrastructure` and then the related kubernetes manifests.
### `clusters`
The `clusters` directory contains all code related to the flux gitops setup in a cluster. The next folder is the name of the cluster. Below is the current layout as of writing this readme.   
```
./clusters/dev # dev cluster
./clusters/prod # prod cluster
```
The flux bootstrap code is automatically generated under `./clusters/$CLUSTER_NAME/flux-system`
## Cluster Setup  
These clusters are created using ansible automation I have. The nodes are all VMs in Proxmox generated by terraform and configured by ansible roles. The roles only provision the cluster to the bare minimum before gitops will function. This includes things like:
* calico - networking
* vault - secrets
* bootstrap prerequisites
