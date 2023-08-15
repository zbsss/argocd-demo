# argocd-demo

## Create Cluster
Create a kind cluster with `extraPortMappings` and `node-labels`.

`extraPortMappings` allow the local host to make requests to the Ingress controller over ports 80/443
`node-labels` only allow the ingress controller to run on a specific node(s) matching the label selector
```
kind create cluster --config deploy/kind-config.yaml
```

## Ingress Example

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

kubectl apply -f https://kind.sigs.k8s.io/examples/ingress/usage.yaml

curl localhost/foo/hostname
curl localhost/bar/hostname

## Commands

```sh
./demo.sh

kubectl get all -A

terraform destroy -auto-approve
```

# TODO
- [ ] Initialize ArgoCD from Terraform
- [ ] Configure nginx ingress from ArgoCD, not from Terraform


# References
1. [Configuring a KinD Cluster with NGINX Ingress Using Terraform and Helm](https://nickjanetakis.com/blog/configuring-a-kind-cluster-with-nginx-ingress-using-terraform-and-helm)
2. [Terraform Provider for kind](https://github.com/tehcyx/terraform-provider-kind)
3. [Manage Kubernetes Cluster with Terraform and Argo CD](https://piotrminkowski.com/2022/06/28/manage-kubernetes-cluster-with-terraform-and-argo-cd/)
4. [Terraform and ArgoCD in beautiful harmony](https://medium.com/@Irori/terraform-and-argocd-in-beautiful-harmony-73c0c6e4544c)
