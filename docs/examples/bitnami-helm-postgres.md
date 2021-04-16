## Add repo

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```

## PostgreSQL Install

postgresql repository [docs](https://github.com/bitnami/charts/tree/master/bitnami/postgresql/#installing-the-chart)

```bash
helm install psql01 -f kubernetes-learning/examples-yaml/bitnami-helm-postgres/postgresql-helm.yml bitnami/postgresql --create-namespace -n postgresql
```

Output, if command succeed

```
NAME: psql01
LAST DEPLOYED: Fri Apr 16 23:53:10 2021
NAMESPACE: postgresql
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
** Please be patient while the chart is being deployed **

PostgreSQL can be accessed via port 5432 on the following DNS name from within your cluster:

    psql01-postgresql.postgresql.svc.cluster.local - Read/Write connection

To get the password for "postgres" run:

    export POSTGRES_ADMIN_PASSWORD=$(kubectl get secret --namespace postgresql psql01-postgresql -o jsonpath="{.data.postgresql-postgres-password}" | base64 --decode)

To get the password for "user" run:

    export POSTGRES_PASSWORD=$(kubectl get secret --namespace postgresql psql01-postgresql -o jsonpath="{.data.postgresql-password}" | base64 --decode)

To connect to your database run the following command:

    kubectl run psql01-postgresql-client --rm --tty -i --restart='Never' --namespace postgresql --image docker.io/bitnami/postgresql:11.11.0-debian-10-r62 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host psql01-postgresql -U user -d exampledb -p 5432



To connect to your database from outside the cluster execute the following commands:

    kubectl port-forward --namespace postgresql svc/psql01-postgresql 5432:5432 &
    PGPASSWORD="$POSTGRES_PASSWORD" psql --host 127.0.0.1 -U user -d exampledb -p 5432
```