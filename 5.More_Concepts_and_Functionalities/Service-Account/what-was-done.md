# We saw that Service Accounts have priviledges and things they can do.

To see what Service Accounts exist we type:
```
kubectl -n argo get serviceaccount
```

To see the rolebingings that exist:
```
kubectl -n argo get rolebindings
```

To get more information about a rolebinding:
```
kubectl -n argo describe rolebinding <<RoleBinding name>>
```

To see the roles:
```
kubectl -n argo get roles
```

To see more information about a role:
```
kubectl -n argo describe role argo-role
```

## To submit a workflow with a service account from the CLI:
```
argo --serviceaccount <<ServiceAccount>> submit <<Workflow to be submitted>>.yaml
```

## Alternatively we can specify the Service Account from the workflow yaml:

On the spec seccion, on the same level as entrypoint we can write:
```
serviceAccountName: <<Service Account>>
```
After this we dont have to use the the serviceaccount argument
