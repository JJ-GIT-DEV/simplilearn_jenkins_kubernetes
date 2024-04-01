# playjenkins
Jenkins Playground


###Deploy Wordpress Application on Kubernetes
====================

This description shows how Jenkins can be used to deploy and roll out Wordpress on Kubernetes.


1. install the kubernetes plugin in jenkins
![install the plugin in jenkins](image.png "plugin installation kubernetes")

2. create new connection to a cloud in jenkins
![create connection to a cloud](image-1.png)

2.1 new cloud name - local_kubernetes
![new cloud name - local_kubernetes](image-2.png)

2.2 config credentials - we use the kube.config file es secrets
![config credentials](image-3.png)

2.3 check connection to kubernetes
![check connection to kubernetes](image-3-1.png)

2.4 add the jenkins URL and tunnel
![add the jenkins URL and tunnel](image-4.png)

2.5 save the configuration fron kubernetes

3 config the pod template
3.1 set the name and label for pod template
![name and label for pod template](image-5.png)

3.2 create container template with jenkinsci/jnlp-slave
![create container template](image-6.png)

4 create credentials for pipeline
4.1 new credentials
![new credentials](image-7.png)

4.2 global credentials add credentials
![global credentials add credentials](image-8.png)

the kubeconfigId should the same as the jenkins pipeline file

"mykubeconfig"
rndran0A@2aafk
the kubeconfig are enter directly. this means you have to use the config from your home. open the terminal and go to the local ~/.kube/config and open it with less config and copy the whole file and add this to jenkins








Configuration in Jenkins for the connection to Kubernetes
-------------------
```
$ mvn jetty:run
```

Open [http://localhost:8080/](http://localhost:8080/)



Configuration in Jenkins for the connection to Kubernetes
-------------------
```
$ mvn jetty:run
```

Open [http://localhost:8080/](http://localhost:8080/)