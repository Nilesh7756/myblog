+++
date = "2017-09-04T13:47:08+02:00"
tags = []
title = "KUBERNETES 101 : Hands on by Examples"
+++


For Creation of [Kubernetes cluster (GKE) on Goolge Cloud Platform please follow link](https://medium.com/google-cloud/how-to-create-google-container-engine-gke-using-the-google-cloud-platform-console-925dd1cc9400).

***Note:*** Do not execute **“kubectl proxy”** command on Google Cloud shell (Work station)

On Google Cloud shell create directory **demo-kube**

    mkdir demo-kube
    cd demo-kube

Create “demo-namespace” [Kubernetes namespace](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)

    wget https://raw.githubusercontent.com/Nilesh7756/k8s-sample-php-demo/master/sample-namespace.yaml

    kubectl create -f sample-namespace.yaml

    kubectl get namespace

Create [Kubernetes Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) for sample php Application

    wget https://raw.githubusercontent.com/Nilesh7756/k8s-sample-php-demo/master/demo-sample-php.yaml
    
    kubectl create -f demo-sample-php.yaml
    
    kubectl get deployment -n demo-namespace

Get [Kubernetes POD](https://kubernetes.io/docs/concepts/workloads/pods/pod/) which were created when deployment kind was created

    kubectl get pods -n demo-namespace

Create [Kubernetes Service](https://kubernetes.io/docs/concepts/services-networking/service/) to access deployment pods externally.

    wget https://raw.githubusercontent.com/Nilesh7756/k8s-sample-php-demo/master/demo-sample-php-svc.yaml

    kubectl create -f demo-sample-php-svc.yaml
    
    kubectl get svc -n demo-namespace

Once external IP recieved from above get command, hit external IP in browser


Delete Kubernetes Resources

    kubectl delete -f demo-sample-php-svc.yaml
    
    kubectl delete -f demo-sample-php.yaml
    
    kubectl delete -f sample-namespace.yaml
