# K8s Ingress with NodePort

Important - LoadBalances does not work on microK8s

```bash
kubectl create namespace test-ingress-nodeport

kubectl apply -f kubernetes-learning/k8s/test-ingress-nodeport/deployment.yml
kubectl apply -f kubernetes-learning/k8s/test-ingress-nodeport/service.yml
kubectl apply -f kubernetes-learning/k8s/test-ingress-nodeport/ingress.yml

kubectl describe svc hello-world-service -n test-ingress-nodeport

kubectl delete namespace test-ingress-nodeport
```

# Sources

* <https://kubernetes.io/docs/tutorials/stateless-application/expose-external-ip-address/>
* <https://stackoverflow.com/questions/58280864/k8s-ingress-for-nodeport-example-for-beginners/58281391#58281391>