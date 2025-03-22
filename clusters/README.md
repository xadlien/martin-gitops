# Clusters
The `clusters` directory contains all code for flux objects in a cluster that are related to flux bootstrapping, or enabling of different applications found elsewhere in the repo.  
The folder structure is as follows:  
`clusters/$CLUSTER_NAME/{infrastructure,apps}/$APPLICATION_NAME.yaml`  
## Enabling Applications for a Cluster
To enable a new app for a cluster, create a file under the related directory. `apps` for applications under the main `apps` directory and similarly for the `infrastructure` applications.