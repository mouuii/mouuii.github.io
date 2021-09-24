---
title: "Kubeconfig"
date: 2021-09-23T19:44:04+08:00
draft: false
categories: k8s
---

### 背景
> 对于多租户多集群需要用到kubeconfig来管理公司人员权限，在k8s官网可以看到，kubeconfig使用了RBAC来
> 授权

### 对于官网文档的学习
To enable RBAC , start the api server with --authorization-mode flag set to a comma-deparated
list that includes RBAC;for example
> kube-apiserver --authorization-mode=Example,RBAC --other-options --more-options

### api objects
rbac api declares four kinds of kubenetes object : 
- role
- clusterRole
- roleBinding
- clusterRoleBinding
  

A Role always sets permissions within a particular namespace; when you create a Role, you have to specify the namespace it belongs in.
If you want to define a role within a namespace, use a Role; if you want to define a role cluster-wide, use a ClusterRole.

