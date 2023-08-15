# argocd-demo

## Ingress Example


## Commands

```sh
terraform apply -auto-approve

curl localhost/foo/hostname
curl localhost/bar/hostname

terraform destroy -auto-approve
```

# ArgoCD UI
```sh
kubectl port-forward service/argocd-server 8443:443 -n argocd

kubectl get secret argocd-initial-admin-secret -n argocd --template={{.data.password}} | base64 -D
```

Open https://localhost:8443 in your browser and login with the password from the previous command.

# TODO
- [x] Initialize ArgoCD from Terraform
- [x] Configure nginx ingress from ArgoCD, not from Terraform


# References
1. [Configuring a KinD Cluster with NGINX Ingress Using Terraform and Helm](https://nickjanetakis.com/blog/configuring-a-kind-cluster-with-nginx-ingress-using-terraform-and-helm)
2. [Terraform Provider for kind](https://github.com/tehcyx/terraform-provider-kind)
3. [Manage Kubernetes Cluster with Terraform and Argo CD](https://piotrminkowski.com/2022/06/28/manage-kubernetes-cluster-with-terraform-and-argo-cd/)
4. [Terraform and ArgoCD in beautiful harmony](https://medium.com/@Irori/terraform-and-argocd-in-beautiful-harmony-73c0c6e4544c)
