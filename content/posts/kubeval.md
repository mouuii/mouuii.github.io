---
title: "Kubeval"
date: 2021-09-24T14:44:32+08:00
draft: false
---
最近公司有需求是要验证k8s yaml 合法性的需求，找了下社区，决定用kubeval，但是kubeval默认会去加载
github上的 json-schema ,导致延迟很高，解决方案，将json-schema下载下来存到公司s3，延迟立马降低，
在接入kubeval golang客户端代码时候使用
```golang
	return kubeval.Validate([]byte(yamlContent), &kubeval.Config{SchemaLocation: "http://resource.koderover.com/k8s-json-scheme", DefaultNamespace: "default", KubernetesVersion: "master"})```