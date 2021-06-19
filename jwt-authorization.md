```
apiVersion: "security.istio.io/v1beta1" 
kind: "AuthorizationPolicy"
metadata:
  name: online-boutique
  namespace: istio-system
spec:
  selector:
    matchLabels:
      istio: ingressgateway
  action: DENY
  rules:
  - when:
    - key: "request.auth.audiences"
      values: ["boutiquestore.com"]
    to:
    - operation:
        paths: ["/cart"]
        ports: ["443"]
---
```
