---
layout: post
title: Microservice with Azure Kubernets Service (AKS) and Azure Devops
---

Microservice with Azure Kubernets Service (AKS) and Azure Devops İzmirde olan etkinlik notlarım.

Onur Yüksektepeli @oyuksektepeli - Microsoft Cloud Solutions Architect - Microsoft MVP (Azure)


# Kubernets

* 150.000 Commits
* 24.000 Contributors
* #1 Github Project

## Microsoft contributions to the community

* Helm
* CNAB
* Porter
* Keda
* Draft
* Vscode Kubernets

azurespeed.com

<hr>

## Azure Kubernets Services - (AKS)

[Create](https://portal.azure.com/#create/microsoft.aks)

`az` = AZURE

```
az aks get-credentials --name NAME --resource-group RESOURCE-GROUP
```

```
az aks browse --name NAME --resource-group RESOURCE-GROUP-rg

```

```
kuberctl get namespaces
```


```
kubectl get pods -n nc-dev
```

## Deployment

### Özet

* Microservices var.
* Deploy'u için yaml yazılır.
* `kubectl get aply -f .\deployment.yaml` olarak çalıştırılır. 

### Örnek

[oyuksektepeli/microservices-demo](https://github.com/oyuksektepeli/microservices-demo)


Yaml Örnekler

[https://github.com/oyuksektepeli/microservices-demo/tree/master/deploy/kubernetes/helm-chart/templates](https://github.com/oyuksektepeli/microservices-demo/tree/master/deploy/kubernetes/helm-chart/templates)





```
kubectl get deployments
```

```
kubectl get aply -f .\deployment.yaml
```

Bu yaml dosyasında kurallar yazılır. podlar servicelerin ruleları yazılır. Eğer 3 tane pod olacak şekilde rule olursa ve 2 tane pod olursa otomatik olarak yeni bir pod oluşturulur.


```
kubectl get pods
```


```
kubectl get service
```

<hr>

DevOps yoksa Microservices olmaz.

<hr>


**Proje Compile Edilme Süreleri**

* debug
* build
* runtime


## Core uygulaması Kubernets'e Deployment

1. Dockerfile container image Hazırla
2. git push and public
3. [https://helm.sh](https://helm.sh) Kubernets package manager kur.

**helm Örnek Wordpress**

```
helm search wordpress

helm fetch stable/wordpress

helm fetch stable/wordpress--untar
```

4. Helm oluştur

```
helm create dockerapp
```

5. Helm package
```
helm package
```

dockerapp helm sh'ı oluşur.


#### Azure Pipline

1. Build an image
2. Push an image
3. Install Helm
4. helm init
5. helm package
6. Publish Artifacts

<hr>

* Commit to Live
* Azure Boards - Jira ve Trello benzeri
* Azure Test - Azure Devops üzerinden Test yazma tool'u.
