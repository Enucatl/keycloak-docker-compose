# keycloak-docker-compose
configuration for a keycloak deployment

## Create truststore with CA public cert

```
keytool -import -alias root_2022_ca \
    -file /home/user/src/puppet-control-repo/modules/ca/files/root_2022_ca.crt \
    -keystore keycloak.truststore \
    -storepass $KEYCLOAK_TLS_TRUSTSTORE_PASSWORD
```
