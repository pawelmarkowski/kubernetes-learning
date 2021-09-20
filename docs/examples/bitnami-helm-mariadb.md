## Add repo

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```

## MariaDBSQL Install

MariaDB-galera repository [docs](https://github.com/bitnami/charts/tree/master/bitnami/mariadb-galera)

```bash
helm install mariadb -f examples-yaml/bitnami-helm/mariadb-galera-helm.yml bitnami/mariadb-galera --create-namespace -n mariadb
```

