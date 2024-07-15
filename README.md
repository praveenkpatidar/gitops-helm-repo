# App of Apps model in ArgoCD

## Follow below steps to install and configure the App of Apps model in ArgoCD

### Tools to install

      Helm
      Kubectl
      Helm Diff
      Helmfile

> In case you are using MacOS Mx, you can use the below image to use helmfile. 

    `praveenkpatidar/devops-utils:latest-macos`

> Follow below steps to run command

    Configure current context to Kubernetes Cluster
    Create env file and run docker command

    `cd <<Directory containing Helm File>>`
    `export CLUSTER=<Name of Cluster>`
    `echo CLUSTER > env`
    `docker run --env-file env -v .:/work -v $HOME/.aws:/root/.aws -v $HOME/.kube:/root/.kube -w /work praveenkpatidar/devops-utils:latest-macos helmfile apply`

## Review all the Entries in value files before running commands below - 
> Cluser name considered in the repo is mycluster

> Change the Folder names mycluster to your cluster name.

> Change the entries in argocd\values\*.yamls argocd\mycluster\argocd-repos.yaml

### Install ArgoCD 
  
    CD argocd
    helmfile apply

### Run Init
    
    CD init
    helmfile apply


