# Miscellaneous

## Bower

### Proxy management

```json
{
    "proxy": "http://<domaine>:<port>",
    "https-proxy": "http://<domaine>:<port>",
    "strict-ssl": false
}
```

`strict-ssl` is only need in the case where the certification validation isn't working because of the proxy. Example of error:

```
bower angular#1.5.3UNABLE_TO_GET_ISSUER_CERT_LOCALLY Request to https://registry.bower.io/packages/angular failed: unable to get local issuer certificate
```
