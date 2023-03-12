# My-Kubernetes-Handbook

**To check all pods in all namespaces**

```kubectl get pods -A```

**To delete all services in a namespace**

```kubectl delete all --all -n {namespace}```

**To get details about the current IAM identity**

```aws sts get-caller-identity``` or ```cat ~/.aws/credentials```

**To get the endpoints of the clusters**

```kubectl get endpoints```

## Start

### Node Groups

**To get NodeGroups for your cluster**

This is basically a Autoscaling group in your AWS account.

```eksctl get nodegroup --cluster $EKS_CLUSTER_NAME --name $EKS_DEFAULT_MNG_NAME```

**To Scale the Node Groups from cli**

You can also do this from AWS Console as well.

```eksctl scale nodegroup --name $EKS_DEFAULT_MNG_NAME --cluster $EKS_CLUSTER_NAME --nodes 3 --nodes-min 3 --nodes-max 6```

**Lists all nodes in our managed node group by using the label as a filter**

```kubectl get nodes -l eks.amazonaws.com/nodegroup=$EKS_DEFAULT_MNG_NAME```


