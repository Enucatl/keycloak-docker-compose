# keycloak-docker-compose
configuration for a keycloak deployment

## Create truststore with CA public cert

```
openssl s_client -connect ipa.home.arpa:636 < /dev/null | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > data/ipa.home.arpa.pem
keytool -import -alias root_2022_ca \
    -file !$ \
    -keystore keycloak.truststore \
    -storepass $KEYCLOAK_TLS_TRUSTSTORE_PASSWORD
```
