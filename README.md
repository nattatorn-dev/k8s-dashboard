## create serviceaccount

$ kubectl create serviceaccount cluster-admin-dashboard
$ kubectl create clusterrolebinding cluster-admin-dashboard \
 --clusterrole=cluster-admin \
 --serviceaccount=default:cluster-admin-dashboard

### Copy the token from the generated secret

$ kubectl get secret | grep cluster-admin-dashboard
cluster-admin-dashboard-token-6xm8l   kubernetes.io/service-account-token   3         18m
$ kubectl describe secret cluster-admin-dashboard-token-tqqr8
