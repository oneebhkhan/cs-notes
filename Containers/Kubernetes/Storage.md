## Persistent Volume
A _PersistentVolume_ (PV) is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using [[Storage Classes]]. It is a resource in the cluster just like a node is a cluster resource. PVs are volume plugins like Volumes, but have a lifecycle independent of any individual Pod that uses the PV. This API object captures the details of the implementation of the storage, be that NFS, iSCSI, or a cloud-provider-specific storage system.


## Persistent Volume Claim
A __PersistentVolumeClaim__ (PVC) is a request for storage by a user. It is similar to a Pod. Pods consume node resources and PVCs consume [[PersistentVolume | PV]]
resources. Pods can request specific levels of resources (CPU and Memory). Claims can request specific size and access modes (e.g., they can be mounted ReadWriteOnce, ReadOnlyMany or ReadWriteMany, see [AccessModes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#access-modes)).

## Storage Classes
