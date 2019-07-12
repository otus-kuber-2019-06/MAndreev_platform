[![Build Status](https://travis-ci.com/otus-kuber-2019-06/MAndreev_platform.svg?branch=master)](https://travis-ci.com/otus-kuber-2019-06/MAndreev_platform)
# MAndreev_platform

## HW 1

 - [x] Main task

#### What was done:
 - Been prepared web-app.yaml to deploy simple web app pod with init container and volumes

#### How to run:
 - to run app
    ```bash
    kubectl apply -f web-app.yaml
    ```
 -  to describe and view pod info
    ```bash
    kubectl describe pod web-app
    kubectl get pod web-app -o yaml # show yaml
    kubectl port-forward --address 0.0.0.0 pod/web-app 8000:8000 # expose 8000 port to host
    kubectl get pods -w
    ```

#### How to check:
 - http://localhost:8000

#### PR checklist:
 - [х] label with HW number

