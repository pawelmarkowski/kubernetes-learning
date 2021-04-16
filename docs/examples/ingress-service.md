# K8s Ingress with NodePort

```bash
kubectl create namespace test-ingress-nodeport

kubectl apply -f kubernetes-learning/examples-yaml/ingress-service/deployment.yml
kubectl apply -f kubernetes-learning/examples-yaml/ingress-service/service.yml
kubectl apply -f kubernetes-learning/examples-yaml/ingress-service/ingress.yml
kubectl describe svc hello-world-service -n test-ingress-nodeport

kubectl delete namespace test-ingress-nodeport
```

## Troubleshooting

```yaml
annotations:
    kubernetes.io/ingress.class: public
```

Service was not accessible through ingress. Extra annotation solved the problem.


# Sources

* <https://kubernetes.io/docs/tutorials/stateless-application/expose-external-ip-address/>
* <https://stackoverflow.com/questions/58280864/k8s-ingress-for-nodeport-example-for-beginners/58281391#58281391>