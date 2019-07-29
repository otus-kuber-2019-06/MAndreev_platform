[![Build Status](https://travis-ci.com/otus-kuber-2019-06/MAndreev_platform.svg?branch=master)](https://travis-ci.com/otus-kuber-2019-06/MAndreev_platform)
# MAndreev_platform

## Tasks

- [x] Create service account bob, with cluster admin role, create service account dave, without cluster permissions  
- [x] Create prometheus namespace, create service account carol, add pod read permissions for all cluster pods for sa in prometheus cluster
- [x] Create dev namespace, add sa jane and ken, jane should be ns admin, ken should has view permissions 

#### What was done:
 - Create service account bob, with cluster admin role, create service account dave, without cluster permissions  
 - Create prometheus namespace, create service account carol, add pod read permissions for all cluster pods for sa in prometheus cluster
 - Create dev namespace, add sa jane and ken, jane should be ns admin, ken should has view permissions

#### How to run:
 - to run app
    ```bash
    for i in 1 2 3; do kubectl apply -f task0${i}; done
    ```

#### How to check:
 - task 1
    ```bash
   for i in create delete deletecollection get list patch update watch; do kubectl auth can-i ${i} pods --as system:serviceaccount:default:bob; done
   for i in create delete deletecollection get list patch update watch; do kubectl auth can-i ${i} pods --as system:serviceaccount:default:dave; done
    ```
 - task 2
     ```bash
    for i in create delete deletecollection get list patch update watch; do kubectl auth can-i ${i} pods --as system:serviceaccount:prometheus:carol -n prometheus; done
     ```
 - task 3
     ```bash
    for i in create delete deletecollection get list patch update watch; do kubectl auth can-i ${i} pods --as system:serviceaccount:dev:ken -n dev; done
    for i in create delete deletecollection get list patch update watch; do kubectl auth can-i ${i} pods --as system:serviceaccount:dev:jane -n dev; done
     ```

#### PR checklist:
 - [x] label with HW number
