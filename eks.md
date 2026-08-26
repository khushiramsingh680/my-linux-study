## Amazon Elastic Kubernetes Service

-  [ ]  First Install aws cli 
```sh
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
```
- [ ] Login on AWS cli
  ```sh
  aws configure
  ```
-  [ ]  How  to connect kuberntes cluster
-  [ ]  You have to have a tool name `kubectl` after dowloading from below link copy to system32
```sh
https://dl.k8s.io/release/v1.36.0/bin/windows/amd64/kubectl.exe
```

-  [ ]  First connect from shell and run
```sh
kubectl get nodes
```

 - [ ]  Download `kubeconfig` file
```sh
aws eks update-kubeconfig --region <region> --name <cluster-name>
aws eks update-kubeconfig --region eu-west-3 --name eks01
```
- [ ] Default location of kubeconfig file is `userhomedir/.kube/config`
- [ ] Use the file from other location
```sh
 kubectl.exe get nodes --kubeconfig config
```
- [ ] Connnect using environment Variable
```sh
export KUBECONFIG=config
```

- [ ]  Deploy one test Application
```sh
kubectl create deployment myapp --image nginx
```
-  [ ] Kubectl get deploy
-  [ ] kubeectl get pod

