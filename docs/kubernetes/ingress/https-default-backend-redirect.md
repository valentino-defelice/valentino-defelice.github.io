# Always redirected to befault backend in https

If no hostname was configured in ingress rule, nginx for HTTPS always redirect to default backend.

## Solution:
Set the hostname in ingress rule.

```
ingress:
  enabled: true
  className: ""
  annotations:
    kubernetes.io/ingress.class: "nginx"
    nginx.ingress.kubernetes.io/rewrite-target: /$2
    #cert-manager.io/cluster-issuer: letsencrypt-staging
    #kubernetes.io/tls-acme: "true"
    #nginx.ingress.kubernetes.io/ssl-passthrough: "true"
    #nginx.ingress.kubernetes.io/backend-protocol: "HTTPs"
    #nginx.ingress.kubernetes.io/ssl-redirect: "true"
  hosts:
    - host: "example.com"
      paths:
        - path: /microservice(/|$)(.*)
          pathType: Prefix
```