![image](https://user-images.githubusercontent.com/528170/122632909-84fa6a00-d08a-11eb-9873-462290085b8b.png)


smaeung2@TMC02CN660MD6R online-boutique % istioctl install --set profile=demo -y
✔ Istio core installed                                                                                                                                                      
✔ Istiod installed                                                                                                                                                          
✔ Egress gateways installed                                                                                                                                                 
✔ Ingress gateways installed                                                                                                                                                
✔ Installation complete                                                                                                                                                     Thank you for installing Istio 1.10.  Please take a few minutes to tell us about your install/upgrade experience!  https://forms.gle/KjkrDnMPByq7akrYA
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system get pods
NAME                                    READY   STATUS    RESTARTS   AGE
istio-egressgateway-659cc7697b-6w5tb    1/1     Running   0          27s
istio-ingressgateway-569f64cdf8-2hz55   1/1     Running   0          27s
istiod-85c958cd6-249gr                  1/1     Running   0          43s
smaeung2@TMC02CN660MD6R online-boutique % kubectl create namespace online-boutique
namespace/online-boutique created
smaeung2@TMC02CN660MD6R online-boutique % kubectl label namespace online-boutique istio-injection=enabled
namespace/online-boutique labeled
smaeung2@TMC02CN660MD6R online-boutique % kubectl apply -n online-boutique -f online-boutique-manifests.yaml 
deployment.apps/emailservice created
service/emailservice created
deployment.apps/checkoutservice created
service/checkoutservice created
deployment.apps/recommendationservice created
service/recommendationservice created
deployment.apps/frontend created
service/frontend created
service/frontend-external created
deployment.apps/paymentservice created
service/paymentservice created
deployment.apps/productcatalogservice created
service/productcatalogservice created
deployment.apps/cartservice created
service/cartservice created
deployment.apps/currencyservice created
service/currencyservice created
deployment.apps/shippingservice created
service/shippingservice created
deployment.apps/redis-cart created
service/redis-cart created
deployment.apps/adservice created
service/adservice created
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          14s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          15s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          15s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          15s
emailservice-8848674-g6d2k               0/2     PodInitializing   0          15s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          15s
paymentservice-77979f5c66-x2pz5          0/2     PodInitializing   0          15s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          15s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          15s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          14s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          15s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          17s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          18s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          18s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          18s
emailservice-8848674-g6d2k               1/2     Running           0          18s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          18s
paymentservice-77979f5c66-x2pz5          0/2     PodInitializing   0          18s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          18s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          18s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          17s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          18s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          18s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          19s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          19s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          19s
emailservice-8848674-g6d2k               1/2     Running           0          19s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          19s
paymentservice-77979f5c66-x2pz5          0/2     PodInitializing   0          19s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          19s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          19s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          18s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          19s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          19s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          20s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          20s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          20s
emailservice-8848674-g6d2k               2/2     Running           0          20s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          20s
paymentservice-77979f5c66-x2pz5          0/2     PodInitializing   0          20s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          20s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          20s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          19s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          20s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          20s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          21s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          21s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          21s
emailservice-8848674-g6d2k               2/2     Running           0          21s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          21s
paymentservice-77979f5c66-x2pz5          0/2     PodInitializing   0          21s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          21s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          21s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          20s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          21s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          21s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          22s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          22s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          22s
emailservice-8848674-g6d2k               2/2     Running           0          22s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          22s
paymentservice-77979f5c66-x2pz5          0/2     PodInitializing   0          22s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          22s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          22s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          21s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          22s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          22s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          23s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          23s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          23s
emailservice-8848674-g6d2k               2/2     Running           0          23s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          23s
paymentservice-77979f5c66-x2pz5          0/2     Running           0          23s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          23s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          23s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          22s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          23s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          22s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          23s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          23s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          23s
emailservice-8848674-g6d2k               2/2     Running           0          23s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          23s
paymentservice-77979f5c66-x2pz5          0/2     Running           0          23s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          23s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          23s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          22s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          23s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          23s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          24s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          24s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          24s
emailservice-8848674-g6d2k               2/2     Running           0          24s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          24s
paymentservice-77979f5c66-x2pz5          1/2     Running           0          24s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          24s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          24s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          23s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          24s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          24s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          25s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          25s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          25s
emailservice-8848674-g6d2k               2/2     Running           0          25s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          25s
paymentservice-77979f5c66-x2pz5          1/2     Running           0          25s
productcatalogservice-7d5f94d858-fbvbx   0/2     PodInitializing   0          25s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          25s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          24s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          25s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          27s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          28s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          28s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          28s
emailservice-8848674-g6d2k               2/2     Running           0          28s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          28s
paymentservice-77979f5c66-x2pz5          1/2     Running           0          28s
productcatalogservice-7d5f94d858-fbvbx   1/2     Running           0          28s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          28s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          27s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          28s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          28s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          29s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          29s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          29s
emailservice-8848674-g6d2k               2/2     Running           0          29s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          29s
paymentservice-77979f5c66-x2pz5          1/2     Running           0          29s
productcatalogservice-7d5f94d858-fbvbx   1/2     Running           0          29s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          29s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          28s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          29s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          28s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          29s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          29s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          29s
emailservice-8848674-g6d2k               2/2     Running           0          29s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          29s
paymentservice-77979f5c66-x2pz5          1/2     Running           0          29s
productcatalogservice-7d5f94d858-fbvbx   1/2     Running           0          29s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          29s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          28s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          29s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          31s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          32s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          32s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          32s
emailservice-8848674-g6d2k               2/2     Running           0          32s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          32s
paymentservice-77979f5c66-x2pz5          1/2     Running           0          32s
productcatalogservice-7d5f94d858-fbvbx   1/2     Running           0          32s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          32s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          31s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          32s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          32s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          33s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          33s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          33s
emailservice-8848674-g6d2k               2/2     Running           0          33s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          33s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          33s
productcatalogservice-7d5f94d858-fbvbx   1/2     Running           0          33s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          33s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          32s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          33s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          34s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          35s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          35s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          35s
emailservice-8848674-g6d2k               2/2     Running           0          35s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          35s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          35s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          35s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          35s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          34s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          35s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          34s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          35s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          35s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          35s
emailservice-8848674-g6d2k               2/2     Running           0          35s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          35s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          35s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          35s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          35s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          34s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          35s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          35s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          36s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          36s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          36s
emailservice-8848674-g6d2k               2/2     Running           0          36s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          36s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          36s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          36s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          36s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          35s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          36s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          36s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          37s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          37s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          37s
emailservice-8848674-g6d2k               2/2     Running           0          37s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          37s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          37s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          37s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          37s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          36s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          37s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          38s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          39s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          39s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          39s
emailservice-8848674-g6d2k               2/2     Running           0          39s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          39s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          39s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          39s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          39s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          38s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          39s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          39s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          40s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          40s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          40s
emailservice-8848674-g6d2k               2/2     Running           0          40s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          40s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          40s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          40s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          40s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          39s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          40s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          40s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          41s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          41s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          41s
emailservice-8848674-g6d2k               2/2     Running           0          41s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          41s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          41s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          41s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          41s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          40s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          41s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          41s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          42s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          42s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          42s
emailservice-8848674-g6d2k               2/2     Running           0          42s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          42s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          42s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          42s
recommendationservice-764dc66688-76qvp   0/2     PodInitializing   0          42s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          41s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          42s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          42s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          43s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          43s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          43s
emailservice-8848674-g6d2k               2/2     Running           0          43s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          43s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          43s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          43s
recommendationservice-764dc66688-76qvp   0/2     Running           0          43s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          42s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          43s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          43s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          44s
checkoutservice-8bddb89db-wpkjk          0/2     PodInitializing   0          44s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          44s
emailservice-8848674-g6d2k               2/2     Running           0          44s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          44s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          44s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          44s
recommendationservice-764dc66688-76qvp   0/2     Running           0          44s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          43s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          44s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          44s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          45s
checkoutservice-8bddb89db-wpkjk          0/2     Running           0          45s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          45s
emailservice-8848674-g6d2k               2/2     Running           0          45s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          45s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          45s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          45s
recommendationservice-764dc66688-76qvp   1/2     Running           0          45s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          44s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          45s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          45s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          46s
checkoutservice-8bddb89db-wpkjk          0/2     Running           0          46s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          46s
emailservice-8848674-g6d2k               2/2     Running           0          46s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          46s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          46s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          46s
recommendationservice-764dc66688-76qvp   1/2     Running           0          46s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          45s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          46s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          45s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          46s
checkoutservice-8bddb89db-wpkjk          0/2     Running           0          46s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          46s
emailservice-8848674-g6d2k               2/2     Running           0          46s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          46s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          46s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          46s
recommendationservice-764dc66688-76qvp   1/2     Running           0          46s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          45s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          46s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          46s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          47s
checkoutservice-8bddb89db-wpkjk          1/2     Running           0          47s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          47s
emailservice-8848674-g6d2k               2/2     Running           0          47s
frontend-58594bf684-7j69b                0/2     PodInitializing   0          47s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          47s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          47s
recommendationservice-764dc66688-76qvp   1/2     Running           0          47s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          46s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          47s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          47s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          48s
checkoutservice-8bddb89db-wpkjk          1/2     Running           0          48s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          48s
emailservice-8848674-g6d2k               2/2     Running           0          48s
frontend-58594bf684-7j69b                0/2     Running           0          48s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          48s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          48s
recommendationservice-764dc66688-76qvp   1/2     Running           0          48s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          47s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          48s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          49s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          50s
checkoutservice-8bddb89db-wpkjk          1/2     Running           0          50s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          50s
emailservice-8848674-g6d2k               2/2     Running           0          50s
frontend-58594bf684-7j69b                1/2     Running           0          50s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          50s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          50s
recommendationservice-764dc66688-76qvp   1/2     Running           0          50s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          49s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          50s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          51s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          52s
checkoutservice-8bddb89db-wpkjk          1/2     Running           0          52s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          52s
emailservice-8848674-g6d2k               2/2     Running           0          52s
frontend-58594bf684-7j69b                1/2     Running           0          52s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          52s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          52s
recommendationservice-764dc66688-76qvp   1/2     Running           0          52s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          51s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          52s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          52s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          53s
checkoutservice-8bddb89db-wpkjk          1/2     Running           0          53s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          53s
emailservice-8848674-g6d2k               2/2     Running           0          53s
frontend-58594bf684-7j69b                1/2     Running           0          53s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          53s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          53s
recommendationservice-764dc66688-76qvp   1/2     Running           0          53s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          52s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          53s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          53s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          54s
checkoutservice-8bddb89db-wpkjk          1/2     Running           0          54s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          54s
emailservice-8848674-g6d2k               2/2     Running           0          54s
frontend-58594bf684-7j69b                1/2     Running           0          54s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          54s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          54s
recommendationservice-764dc66688-76qvp   2/2     Running           0          54s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          53s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          54s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          54s
cartservice-65c987d449-mrh54             0/2     PodInitializing   0          55s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          55s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          55s
emailservice-8848674-g6d2k               2/2     Running           0          55s
frontend-58594bf684-7j69b                1/2     Running           0          55s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          55s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          55s
recommendationservice-764dc66688-76qvp   2/2     Running           0          55s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          54s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          55s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          55s
cartservice-65c987d449-mrh54             0/2     Running           0          56s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          56s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          56s
emailservice-8848674-g6d2k               2/2     Running           0          56s
frontend-58594bf684-7j69b                1/2     Running           0          56s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          56s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          56s
recommendationservice-764dc66688-76qvp   2/2     Running           0          56s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          55s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          56s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          57s
cartservice-65c987d449-mrh54             1/2     NotReady          0          58s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          58s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          58s
emailservice-8848674-g6d2k               2/2     Running           0          58s
frontend-58594bf684-7j69b                1/2     Running           0          58s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          58s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          58s
recommendationservice-764dc66688-76qvp   2/2     Running           0          58s
redis-cart-74594bd569-sw5cj              0/2     PodInitializing   0          57s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          58s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          59s
cartservice-65c987d449-mrh54             1/2     Running           1          60s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          60s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          60s
emailservice-8848674-g6d2k               2/2     Running           0          60s
frontend-58594bf684-7j69b                1/2     Running           0          60s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          60s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          60s
recommendationservice-764dc66688-76qvp   2/2     Running           0          60s
redis-cart-74594bd569-sw5cj              0/2     Running           0          59s
shippingservice-589dc45c5d-42sqv         0/2     PodInitializing   0          60s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          60s
cartservice-65c987d449-mrh54             1/2     Running           1          61s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          61s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          61s
emailservice-8848674-g6d2k               2/2     Running           0          61s
frontend-58594bf684-7j69b                1/2     Running           0          61s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          61s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          61s
recommendationservice-764dc66688-76qvp   2/2     Running           0          61s
redis-cart-74594bd569-sw5cj              1/2     Running           0          60s
shippingservice-589dc45c5d-42sqv         0/2     Running           0          61s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          61s
cartservice-65c987d449-mrh54             1/2     NotReady          1          62s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          62s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          62s
emailservice-8848674-g6d2k               2/2     Running           0          62s
frontend-58594bf684-7j69b                2/2     Running           0          62s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          62s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          62s
recommendationservice-764dc66688-76qvp   2/2     Running           0          62s
redis-cart-74594bd569-sw5cj              2/2     Running           0          61s
shippingservice-589dc45c5d-42sqv         0/2     Running           0          62s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          61s
cartservice-65c987d449-mrh54             1/2     NotReady          1          62s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          62s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing   0          62s
emailservice-8848674-g6d2k               2/2     Running           0          62s
frontend-58594bf684-7j69b                2/2     Running           0          62s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          62s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          62s
recommendationservice-764dc66688-76qvp   2/2     Running           0          62s
redis-cart-74594bd569-sw5cj              2/2     Running           0          61s
shippingservice-589dc45c5d-42sqv         1/2     Running           0          62s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          62s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          63s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          63s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing    0          63s
emailservice-8848674-g6d2k               2/2     Running            0          63s
frontend-58594bf684-7j69b                2/2     Running            0          63s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          63s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          63s
recommendationservice-764dc66688-76qvp   2/2     Running            0          63s
redis-cart-74594bd569-sw5cj              2/2     Running            0          62s
shippingservice-589dc45c5d-42sqv         1/2     Running            0          63s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          63s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          64s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          64s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing    0          64s
emailservice-8848674-g6d2k               2/2     Running            0          64s
frontend-58594bf684-7j69b                2/2     Running            0          64s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          64s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          64s
recommendationservice-764dc66688-76qvp   2/2     Running            0          64s
redis-cart-74594bd569-sw5cj              2/2     Running            0          63s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          64s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          64s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          65s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          65s
currencyservice-7978fb77d8-94cv6         0/2     PodInitializing    0          65s
emailservice-8848674-g6d2k               2/2     Running            0          65s
frontend-58594bf684-7j69b                2/2     Running            0          65s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          65s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          65s
recommendationservice-764dc66688-76qvp   2/2     Running            0          65s
redis-cart-74594bd569-sw5cj              2/2     Running            0          64s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          65s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          65s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          66s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          66s
currencyservice-7978fb77d8-94cv6         0/2     Running            0          66s
emailservice-8848674-g6d2k               2/2     Running            0          66s
frontend-58594bf684-7j69b                2/2     Running            0          66s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          66s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          66s
recommendationservice-764dc66688-76qvp   2/2     Running            0          66s
redis-cart-74594bd569-sw5cj              2/2     Running            0          65s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          66s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          66s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          67s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          67s
currencyservice-7978fb77d8-94cv6         0/2     Running            0          67s
emailservice-8848674-g6d2k               2/2     Running            0          67s
frontend-58594bf684-7j69b                2/2     Running            0          67s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          67s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          67s
recommendationservice-764dc66688-76qvp   2/2     Running            0          67s
redis-cart-74594bd569-sw5cj              2/2     Running            0          66s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          67s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          67s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          68s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          68s
currencyservice-7978fb77d8-94cv6         1/2     Running            0          68s
emailservice-8848674-g6d2k               2/2     Running            0          68s
frontend-58594bf684-7j69b                2/2     Running            0          68s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          68s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          68s
recommendationservice-764dc66688-76qvp   2/2     Running            0          68s
redis-cart-74594bd569-sw5cj              2/2     Running            0          67s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          68s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          68s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          69s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          69s
currencyservice-7978fb77d8-94cv6         1/2     Running            0          69s
emailservice-8848674-g6d2k               2/2     Running            0          69s
frontend-58594bf684-7j69b                2/2     Running            0          69s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          69s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          69s
recommendationservice-764dc66688-76qvp   2/2     Running            0          69s
redis-cart-74594bd569-sw5cj              2/2     Running            0          68s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          69s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          71s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          72s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          72s
currencyservice-7978fb77d8-94cv6         1/2     Running            0          72s
emailservice-8848674-g6d2k               2/2     Running            0          72s
frontend-58594bf684-7j69b                2/2     Running            0          72s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          72s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          72s
recommendationservice-764dc66688-76qvp   2/2     Running            0          72s
redis-cart-74594bd569-sw5cj              2/2     Running            0          71s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          72s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          72s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          73s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          73s
currencyservice-7978fb77d8-94cv6         1/2     Running            0          73s
emailservice-8848674-g6d2k               2/2     Running            0          73s
frontend-58594bf684-7j69b                2/2     Running            0          73s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          73s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          73s
recommendationservice-764dc66688-76qvp   2/2     Running            0          73s
redis-cart-74594bd569-sw5cj              2/2     Running            0          72s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          73s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          73s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          74s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          74s
currencyservice-7978fb77d8-94cv6         1/2     Running            0          74s
emailservice-8848674-g6d2k               2/2     Running            0          74s
frontend-58594bf684-7j69b                2/2     Running            0          74s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          74s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          74s
recommendationservice-764dc66688-76qvp   2/2     Running            0          74s
redis-cart-74594bd569-sw5cj              2/2     Running            0          73s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          74s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          73s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          74s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          74s
currencyservice-7978fb77d8-94cv6         1/2     Running            0          74s
emailservice-8848674-g6d2k               2/2     Running            0          74s
frontend-58594bf684-7j69b                2/2     Running            0          74s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          74s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          74s
recommendationservice-764dc66688-76qvp   2/2     Running            0          74s
redis-cart-74594bd569-sw5cj              2/2     Running            0          73s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          74s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          74s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          75s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          75s
currencyservice-7978fb77d8-94cv6         1/2     Running            0          75s
emailservice-8848674-g6d2k               2/2     Running            0          75s
frontend-58594bf684-7j69b                2/2     Running            0          75s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          75s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          75s
recommendationservice-764dc66688-76qvp   2/2     Running            0          75s
redis-cart-74594bd569-sw5cj              2/2     Running            0          74s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          75s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          75s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          76s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          76s
currencyservice-7978fb77d8-94cv6         1/2     Running            0          76s
emailservice-8848674-g6d2k               2/2     Running            0          76s
frontend-58594bf684-7j69b                2/2     Running            0          76s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          76s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          76s
recommendationservice-764dc66688-76qvp   2/2     Running            0          76s
redis-cart-74594bd569-sw5cj              2/2     Running            0          75s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          76s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS             RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing    0          75s
cartservice-65c987d449-mrh54             1/2     CrashLoopBackOff   1          76s
checkoutservice-8bddb89db-wpkjk          2/2     Running            0          76s
currencyservice-7978fb77d8-94cv6         2/2     Running            0          76s
emailservice-8848674-g6d2k               2/2     Running            0          76s
frontend-58594bf684-7j69b                2/2     Running            0          76s
paymentservice-77979f5c66-x2pz5          2/2     Running            0          76s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running            0          76s
recommendationservice-764dc66688-76qvp   2/2     Running            0          76s
redis-cart-74594bd569-sw5cj              2/2     Running            0          75s
shippingservice-589dc45c5d-42sqv         2/2     Running            0          76s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          76s
cartservice-65c987d449-mrh54             1/2     Running           2          77s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          77s
currencyservice-7978fb77d8-94cv6         2/2     Running           0          77s
emailservice-8848674-g6d2k               2/2     Running           0          77s
frontend-58594bf684-7j69b                2/2     Running           0          77s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          77s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          77s
recommendationservice-764dc66688-76qvp   2/2     Running           0          77s
redis-cart-74594bd569-sw5cj              2/2     Running           0          76s
shippingservice-589dc45c5d-42sqv         2/2     Running           0          77s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          77s
cartservice-65c987d449-mrh54             1/2     Running           2          78s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          78s
currencyservice-7978fb77d8-94cv6         2/2     Running           0          78s
emailservice-8848674-g6d2k               2/2     Running           0          78s
frontend-58594bf684-7j69b                2/2     Running           0          78s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          78s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          78s
recommendationservice-764dc66688-76qvp   2/2     Running           0          78s
redis-cart-74594bd569-sw5cj              2/2     Running           0          77s
shippingservice-589dc45c5d-42sqv         2/2     Running           0          78s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          78s
cartservice-65c987d449-mrh54             1/2     Running           2          79s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          79s
currencyservice-7978fb77d8-94cv6         2/2     Running           0          79s
emailservice-8848674-g6d2k               2/2     Running           0          79s
frontend-58594bf684-7j69b                2/2     Running           0          79s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          79s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          79s
recommendationservice-764dc66688-76qvp   2/2     Running           0          79s
redis-cart-74594bd569-sw5cj              2/2     Running           0          78s
shippingservice-589dc45c5d-42sqv         2/2     Running           0          79s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS            RESTARTS   AGE
adservice-7659d48d84-f9htp               0/2     PodInitializing   0          79s
cartservice-65c987d449-mrh54             1/2     Running           2          80s
checkoutservice-8bddb89db-wpkjk          2/2     Running           0          80s
currencyservice-7978fb77d8-94cv6         2/2     Running           0          80s
emailservice-8848674-g6d2k               2/2     Running           0          80s
frontend-58594bf684-7j69b                2/2     Running           0          80s
paymentservice-77979f5c66-x2pz5          2/2     Running           0          80s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running           0          80s
recommendationservice-764dc66688-76qvp   2/2     Running           0          80s
redis-cart-74594bd569-sw5cj              2/2     Running           0          79s
shippingservice-589dc45c5d-42sqv         2/2     Running           0          80s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS    RESTARTS   AGE
adservice-7659d48d84-f9htp               1/2     Running   0          83s
cartservice-65c987d449-mrh54             1/2     Running   2          84s
checkoutservice-8bddb89db-wpkjk          2/2     Running   0          84s
currencyservice-7978fb77d8-94cv6         2/2     Running   0          84s
emailservice-8848674-g6d2k               2/2     Running   0          84s
frontend-58594bf684-7j69b                2/2     Running   0          84s
paymentservice-77979f5c66-x2pz5          2/2     Running   0          84s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running   0          84s
recommendationservice-764dc66688-76qvp   2/2     Running   0          84s
redis-cart-74594bd569-sw5cj              2/2     Running   0          83s
shippingservice-589dc45c5d-42sqv         2/2     Running   0          84s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS    RESTARTS   AGE
adservice-7659d48d84-f9htp               1/2     Running   0          84s
cartservice-65c987d449-mrh54             1/2     Running   2          85s
checkoutservice-8bddb89db-wpkjk          2/2     Running   0          85s
currencyservice-7978fb77d8-94cv6         2/2     Running   0          85s
emailservice-8848674-g6d2k               2/2     Running   0          85s
frontend-58594bf684-7j69b                2/2     Running   0          85s
paymentservice-77979f5c66-x2pz5          2/2     Running   0          85s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running   0          85s
recommendationservice-764dc66688-76qvp   2/2     Running   0          85s
redis-cart-74594bd569-sw5cj              2/2     Running   0          84s
shippingservice-589dc45c5d-42sqv         2/2     Running   0          85s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS    RESTARTS   AGE
adservice-7659d48d84-f9htp               1/2     Running   0          86s
cartservice-65c987d449-mrh54             1/2     Running   2          87s
checkoutservice-8bddb89db-wpkjk          2/2     Running   0          87s
currencyservice-7978fb77d8-94cv6         2/2     Running   0          87s
emailservice-8848674-g6d2k               2/2     Running   0          87s
frontend-58594bf684-7j69b                2/2     Running   0          87s
paymentservice-77979f5c66-x2pz5          2/2     Running   0          87s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running   0          87s
recommendationservice-764dc66688-76qvp   2/2     Running   0          87s
redis-cart-74594bd569-sw5cj              2/2     Running   0          86s
shippingservice-589dc45c5d-42sqv         2/2     Running   0          87s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS    RESTARTS   AGE
adservice-7659d48d84-f9htp               1/2     Running   0          88s
cartservice-65c987d449-mrh54             1/2     Running   2          89s
checkoutservice-8bddb89db-wpkjk          2/2     Running   0          89s
currencyservice-7978fb77d8-94cv6         2/2     Running   0          89s
emailservice-8848674-g6d2k               2/2     Running   0          89s
frontend-58594bf684-7j69b                2/2     Running   0          89s
paymentservice-77979f5c66-x2pz5          2/2     Running   0          89s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running   0          89s
recommendationservice-764dc66688-76qvp   2/2     Running   0          89s
redis-cart-74594bd569-sw5cj              2/2     Running   0          88s
shippingservice-589dc45c5d-42sqv         2/2     Running   0          89s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system get svc istio-ingressgateway
NAME                   TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)                                                                      AGE
istio-ingressgateway   LoadBalancer   10.110.134.150   <pending>     15021:32176/TCP,80:32338/TCP,443:32126/TCP,31400:32261/TCP,15443:31962/TCP   3m58s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system get svc istio-ingressgateway
NAME                   TYPE           CLUSTER-IP       EXTERNAL-IP      PORT(S)                                                                      AGE
istio-ingressgateway   LoadBalancer   10.110.134.150   10.110.134.150   15021:32176/TCP,80:32338/TCP,443:32126/TCP,31400:32261/TCP,15443:31962/TCP   4m22s
smaeung2@TMC02CN660MD6R online-boutique % sour ingress_script.sh 
zsh: command not found: sour
smaeung2@TMC02CN660MD6R online-boutique % more ingress_script.sh 
export INGRESS=$(kubectl -n istio-system get svc istio-ingressgateway \
  -o jsonpath='{.status.loadBalancer.ingress[0].ip}')
smaeung2@TMC02CN660MD6R online-boutique % export INGRESS=$(kubectl -n istio-system get svc istio-ingressgateway \
  -o jsonpath='{.status.loadBalancer.ingress[0].ip}')
smaeung2@TMC02CN660MD6R online-boutique % echo $INGRESS
10.110.134.150
smaeung2@TMC02CN660MD6R online-boutique % kubectl apply -n online-boutique -f - << EOF
apiVersion: networking.istio.io/v1beta1
kind: Gateway
metadata:
  name: frontend-gateway
  namespace: online-boutique
spec:
  selector:
    # use Istio default gateway implementation
    istio: ingressgateway
  servers:
  - port:
      number: 80
      name: http
      protocol: HTTP
    hosts:
    - "*"
EOF
gateway.networking.istio.io/frontend-gateway created
smaeung2@TMC02CN660MD6R online-boutique % kubectl apply -n online-boutique -f - << EOF
apiVersion: networking.istio.io/v1alpha3
kind: VirtualService
metadata:
  name: frontend-virtual-service
  namespace: online-boutique
spec:
  hosts:
  - "*"
  gateways:
  - frontend-gateway
  http:
  - route:
    - destination:
        host: frontend
        port:
          number: 80
EOF
virtualservice.networking.istio.io/frontend-virtual-service created
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get svc frontend -o yaml
apiVersion: v1
kind: Service
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"v1","kind":"Service","metadata":{"annotations":{},"name":"frontend","namespace":"online-boutique"},"spec":{"ports":[{"name":"http","port":80,"targetPort":8080}],"selector":{"app":"frontend"},"type":"ClusterIP"}}
  creationTimestamp: "2021-06-19T05:44:22Z"
  managedFields:
  - apiVersion: v1
    fieldsType: FieldsV1
    fieldsV1:
      f:metadata:
        f:annotations:
          .: {}
          f:kubectl.kubernetes.io/last-applied-configuration: {}
      f:spec:
        f:ports:
          .: {}
          k:{"port":80,"protocol":"TCP"}:
            .: {}
            f:name: {}
            f:port: {}
            f:protocol: {}
            f:targetPort: {}
        f:selector:
          .: {}
          f:app: {}
        f:sessionAffinity: {}
        f:type: {}
    manager: kubectl-client-side-apply
    operation: Update
    time: "2021-06-19T05:44:22Z"
  name: frontend
  namespace: online-boutique
  resourceVersion: "849"
  uid: 81a3c617-9e46-4a1b-91a3-f64b6f77809e
spec:
  clusterIP: 10.103.242.245
  clusterIPs:
  - 10.103.242.245
  ports:
  - name: http
    port: 80
    protocol: TCP
    targetPort: 8080
  selector:
    app: frontend
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
smaeung2@TMC02CN660MD6R online-boutique % echo $INGRESS                                      
10.110.134.150
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique apply -f frontend-v2.yaml 
deployment.apps/frontend-v2 created
service/frontend-v2 created
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods
NAME                                     READY   STATUS    RESTARTS   AGE
adservice-7659d48d84-f9htp               2/2     Running   0          8m42s
cartservice-65c987d449-mrh54             2/2     Running   2          8m43s
checkoutservice-8bddb89db-wpkjk          2/2     Running   0          8m43s
currencyservice-7978fb77d8-94cv6         2/2     Running   0          8m43s
emailservice-8848674-g6d2k               2/2     Running   0          8m43s
frontend-58594bf684-7j69b                2/2     Running   0          8m43s
frontend-v2-7b487c988d-lcss2             1/2     Running   0          15s
paymentservice-77979f5c66-x2pz5          2/2     Running   0          8m43s
productcatalogservice-7d5f94d858-fbvbx   2/2     Running   0          8m43s
recommendationservice-764dc66688-76qvp   2/2     Running   0          8m43s
redis-cart-74594bd569-sw5cj              2/2     Running   0          8m42s
shippingservice-589dc45c5d-42sqv         2/2     Running   0          8m43s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get endpoints frontend-v2
NAME          ENDPOINTS          AGE
frontend-v2   172.17.0.17:8080   57s
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get endpoints frontend
NAME       ENDPOINTS          AGE
frontend   172.17.0.11:8080   9m42s
smaeung2@TMC02CN660MD6R online-boutique % kubectl apply -n online-boutique -f - << EOF
apiVersion: networking.istio.io/v1alpha3
kind: VirtualService
metadata:
  name: frontend-virtual-service
  namespace: online-boutique
spec:
  hosts:
  - "*"
  gateways:
  - frontend-gateway
  http:
  - route:
    - destination:
        host: frontend
        port:
          number: 80
      weight: 50
    - destination:
        host: frontend-v2
        port:
          number: 80
      weight: 50
EOF
virtualservice.networking.istio.io/frontend-virtual-service configured
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique get pods         
NAME                                     READY   STATUS    RESTARTS   AGE
adservice-7659d48d84-f9htp               2/2     Running   0          13m
cartservice-65c987d449-mrh54             2/2     Running   2          13m
checkoutservice-8bddb89db-wpkjk          2/2     Running   0          13m
currencyservice-7978fb77d8-94cv6         2/2     Running   0          13m
emailservice-8848674-g6d2k               2/2     Running   0          13m
frontend-58594bf684-7j69b                2/2     Running   0          13m
frontend-v2-7b487c988d-lcss2             2/2     Running   0          4m48s
paymentservice-77979f5c66-x2pz5          2/2     Running   0          13m
productcatalogservice-7d5f94d858-fbvbx   2/2     Running   0          13m
recommendationservice-764dc66688-76qvp   2/2     Running   0          13m
redis-cart-74594bd569-sw5cj              2/2     Running   0          13m
shippingservice-589dc45c5d-42sqv         2/2     Running   0          13m
smaeung2@TMC02CN660MD6R online-boutique % istioctl install --set profile=demo -set meshConfig.accessLogFile="/dev/stdout" --set meshConfig.accessLogEncoding=JSON -y
Error: accepts 0 arg(s), received 1
smaeung2@TMC02CN660MD6R online-boutique % istioctl install --set profile=demo --set meshConfig.accessLogFile="/dev/stdout" --set meshConfig.accessLogEncoding=JSON -y
✔ Istio core installed                                                                                                                                                      
✔ Istiod installed                                                                                                                                                          
✔ Egress gateways installed                                                                                                                                                 
✔ Ingress gateways installed                                                                                                                                                
✔ Installation complete                                                                                                                                                     Thank you for installing Istio 1.10.  Please take a few minutes to tell us about your install/upgrade experience!  https://forms.gle/KjkrDnMPByq7akrYA
smaeung2@TMC02CN660MD6R online-boutique % kubectl logs
error: expected 'logs [-f] [-p] (POD | TYPE/NAME) [-c CONTAINER]'.
POD or TYPE/NAME is a required argument for the logs command
See 'kubectl logs -h' for help and examples
smaeung2@TMC02CN660MD6R online-boutique % kubectl logs -h
Print the logs for a container in a pod or specified resource. If the pod has only one container, the container name is
optional.

Examples:
  # Return snapshot logs from pod nginx with only one container
  kubectl logs nginx
  
  # Return snapshot logs from pod nginx with multi containers
  kubectl logs nginx --all-containers=true
  
  # Return snapshot logs from all containers in pods defined by label app=nginx
  kubectl logs -lapp=nginx --all-containers=true
  
  # Return snapshot of previous terminated ruby container logs from pod web-1
  kubectl logs -p -c ruby web-1
  
  # Begin streaming the logs of the ruby container in pod web-1
  kubectl logs -f -c ruby web-1
  
  # Begin streaming the logs from all containers in pods defined by label app=nginx
  kubectl logs -f -lapp=nginx --all-containers=true
  
  # Display only the most recent 20 lines of output in pod nginx
  kubectl logs --tail=20 nginx
  
  # Show all logs from pod nginx written in the last hour
  kubectl logs --since=1h nginx
  
  # Show logs from a kubelet with an expired serving certificate
  kubectl logs --insecure-skip-tls-verify-backend nginx
  
  # Return snapshot logs from first container of a job named hello
  kubectl logs job/hello
  
  # Return snapshot logs from container nginx-1 of a deployment named nginx
  kubectl logs deployment/nginx -c nginx-1

Options:
      --all-containers=false: Get all containers' logs in the pod(s).
  -c, --container='': Print the logs of this container
  -f, --follow=false: Specify if the logs should be streamed.
      --ignore-errors=false: If watching / following pod logs, allow for any errors that occur to be non-fatal
      --insecure-skip-tls-verify-backend=false: Skip verifying the identity of the kubelet that logs are requested from.
In theory, an attacker could provide invalid log content back. You might want to use this if your kubelet serving
certificates have expired.
      --limit-bytes=0: Maximum bytes of logs to return. Defaults to no limit.
      --max-log-requests=5: Specify maximum number of concurrent logs to follow when using by a selector. Defaults to 5.
      --pod-running-timeout=20s: The length of time (like 5s, 2m, or 3h, higher than zero) to wait until at least one
pod is running
      --prefix=false: Prefix each log line with the log source (pod name and container name)
  -p, --previous=false: If true, print the logs for the previous instance of the container in a pod if it exists.
  -l, --selector='': Selector (label query) to filter on.
      --since=0s: Only return logs newer than a relative duration like 5s, 2m, or 3h. Defaults to all logs. Only one of
since-time / since may be used.
      --since-time='': Only return logs after a specific date (RFC3339). Defaults to all logs. Only one of since-time /
since may be used.
      --tail=-1: Lines of recent log file to display. Defaults to -1 with no selector, showing all log lines otherwise
10, if a selector is provided.
      --timestamps=false: Include timestamps on each line in the log output

Usage:
  kubectl logs [-f] [-p] (POD | TYPE/NAME) [-c CONTAINER] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system logs -l app=istio-ingressgateway
[2021-06-19T05:58:11.161Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 58 57 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "f4648867-7d0a-9238-92f1-e15a5383f851" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:11.324Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "a10e11c8-a56a-9822-b3b6-b5c2708618c9" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.051Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 37 36 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "99fabf34-f3c1-9e48-8fe1-f1ef8db5e48a" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.188Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "8b0ae822-1490-9098-992a-438a886bd59f" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.782Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 38 38 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "0d28c082-9ad5-9080-a39f-a74b1e6523b7" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.927Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "9e4d0710-9705-92d8-8567-7b2411a2defe" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.389Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 35 34 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "b34c6b91-5c99-99f5-aacd-0d15e0ccd9f3" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.526Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "50d46e1d-629b-9708-9a0a-c0788a1c8362" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.896Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 43 43 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "44b704b6-4a3d-9a30-9f89-43e767e84c5f" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:14.045Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "ce0c7b6e-ec59-9859-a9f9-9b9970e04171" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system logs -l app=istio-ingressgateway
[2021-06-19T05:58:11.161Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 58 57 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "f4648867-7d0a-9238-92f1-e15a5383f851" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:11.324Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "a10e11c8-a56a-9822-b3b6-b5c2708618c9" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.051Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 37 36 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "99fabf34-f3c1-9e48-8fe1-f1ef8db5e48a" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.188Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "8b0ae822-1490-9098-992a-438a886bd59f" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.782Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 38 38 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "0d28c082-9ad5-9080-a39f-a74b1e6523b7" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.927Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "9e4d0710-9705-92d8-8567-7b2411a2defe" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.389Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 35 34 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "b34c6b91-5c99-99f5-aacd-0d15e0ccd9f3" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.526Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "50d46e1d-629b-9708-9a0a-c0788a1c8362" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.896Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 43 43 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "44b704b6-4a3d-9a30-9f89-43e767e84c5f" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:14.045Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "ce0c7b6e-ec59-9859-a9f9-9b9970e04171" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system logs -l app=istio-ingressgateway
[2021-06-19T05:58:11.161Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 58 57 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "f4648867-7d0a-9238-92f1-e15a5383f851" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:11.324Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "a10e11c8-a56a-9822-b3b6-b5c2708618c9" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.051Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 37 36 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "99fabf34-f3c1-9e48-8fe1-f1ef8db5e48a" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.188Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "8b0ae822-1490-9098-992a-438a886bd59f" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.782Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 38 38 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "0d28c082-9ad5-9080-a39f-a74b1e6523b7" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.927Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "9e4d0710-9705-92d8-8567-7b2411a2defe" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.389Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 35 34 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "b34c6b91-5c99-99f5-aacd-0d15e0ccd9f3" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.526Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "50d46e1d-629b-9708-9a0a-c0788a1c8362" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.896Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 43 43 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "44b704b6-4a3d-9a30-9f89-43e767e84c5f" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:14.045Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "ce0c7b6e-ec59-9859-a9f9-9b9970e04171" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system logs -l app=istio-ingressgateway
^[[A
[2021-06-19T05:58:11.161Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 58 57 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "f4648867-7d0a-9238-92f1-e15a5383f851" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:11.324Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "a10e11c8-a56a-9822-b3b6-b5c2708618c9" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.051Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 37 36 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "99fabf34-f3c1-9e48-8fe1-f1ef8db5e48a" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.188Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "8b0ae822-1490-9098-992a-438a886bd59f" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.782Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 38 38 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "0d28c082-9ad5-9080-a39f-a74b1e6523b7" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.927Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "9e4d0710-9705-92d8-8567-7b2411a2defe" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.389Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 35 34 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "b34c6b91-5c99-99f5-aacd-0d15e0ccd9f3" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.526Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "50d46e1d-629b-9708-9a0a-c0788a1c8362" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.896Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 43 43 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "44b704b6-4a3d-9a30-9f89-43e767e84c5f" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:14.045Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "ce0c7b6e-ec59-9859-a9f9-9b9970e04171" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system logs -l app=istio-ingressgateway
[2021-06-19T05:58:11.161Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 58 57 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "f4648867-7d0a-9238-92f1-e15a5383f851" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:11.324Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "a10e11c8-a56a-9822-b3b6-b5c2708618c9" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.051Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 37 36 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "99fabf34-f3c1-9e48-8fe1-f1ef8db5e48a" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.188Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "8b0ae822-1490-9098-992a-438a886bd59f" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.782Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 38 38 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "0d28c082-9ad5-9080-a39f-a74b1e6523b7" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.927Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "9e4d0710-9705-92d8-8567-7b2411a2defe" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.389Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 35 34 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "b34c6b91-5c99-99f5-aacd-0d15e0ccd9f3" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.526Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "50d46e1d-629b-9708-9a0a-c0788a1c8362" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.896Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 43 43 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "44b704b6-4a3d-9a30-9f89-43e767e84c5f" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:14.045Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "ce0c7b6e-ec59-9859-a9f9-9b9970e04171" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n istio-system logs -l app=istio-ingressgateway
[2021-06-19T05:58:11.161Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 58 57 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "f4648867-7d0a-9238-92f1-e15a5383f851" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:11.324Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "a10e11c8-a56a-9822-b3b6-b5c2708618c9" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.051Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 37 36 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "99fabf34-f3c1-9e48-8fe1-f1ef8db5e48a" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.188Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "8b0ae822-1490-9098-992a-438a886bd59f" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.782Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 38 38 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "0d28c082-9ad5-9080-a39f-a74b1e6523b7" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:12.927Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 1 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "9e4d0710-9705-92d8-8567-7b2411a2defe" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.389Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 35 34 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "b34c6b91-5c99-99f5-aacd-0d15e0ccd9f3" "10.110.134.150" "172.17.0.11:8080" outbound|80||frontend.online-boutique.svc.cluster.local 172.17.0.4:49402 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.526Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 1 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "50d46e1d-629b-9708-9a0a-c0788a1c8362" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:13.896Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10799 43 43 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "44b704b6-4a3d-9a30-9f89-43e767e84c5f" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
[2021-06-19T05:58:14.045Z] "GET /static/favicon.ico HTTP/1.1" 200 - via_upstream - "-" 0 16958 2 2 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "ce0c7b6e-ec59-9859-a9f9-9b9970e04171" "10.110.134.150" "172.17.0.17:8080" outbound|80||frontend-v2.online-boutique.svc.cluster.local 172.17.0.4:49104 172.17.0.4:8080 172.17.0.1:42760 - -
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique logs -l app=frontend -c istio-proxy
[2021-06-19T05:58:13.400Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 1 1 "-" "grpc-go/1.22.0" "e17d6852-53c1-9894-ba8f-90757233ed91" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.402Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 19 18 1 1 "-" "grpc-go/1.22.0" "4a4ff706-b561-94ff-a14e-c1dfeee9825d" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.405Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 1 1 "-" "grpc-go/1.22.0" "5bd26972-a658-9210-b180-fae943343271" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.407Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 20 19 1 1 "-" "grpc-go/1.22.0" "fa642397-bd8c-99e5-ad6b-bac46f9a24b8" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.409Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 1 1 "-" "grpc-go/1.22.0" "6dd96c2a-c959-9c1c-bea8-0d7b4d681dbe" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.411Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 1 1 "-" "grpc-go/1.22.0" "382dc765-2a8c-9fc7-9c36-c3fd1cd75818" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.413Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 26 19 1 1 "-" "grpc-go/1.22.0" "b15aab75-15e4-9050-a504-245df1d99f8a" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.415Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 2 2 "-" "grpc-go/1.22.0" "c7e392ad-4843-9a0e-a031-755f2eba3520" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.419Z] "POST /hipstershop.AdService/GetAds HTTP/2" 200 - via_upstream - "-" 5 123 3 2 "-" "grpc-go/1.22.0" "0a353dee-e565-99bd-baf0-15e4fca731cf" "adservice:9555" "172.17.0.16:9555" outbound|9555||adservice.online-boutique.svc.cluster.local 172.17.0.11:37328 10.101.204.176:9555 172.17.0.11:40490 - default
[2021-06-19T05:58:13.389Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 34 33 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "b34c6b91-5c99-99f5-aacd-0d15e0ccd9f3" "10.110.134.150" "172.17.0.11:8080" inbound|8080|| 127.0.0.6:53023 172.17.0.11:8080 172.17.0.1:0 outbound_.80_._.frontend.online-boutique.svc.cluster.local default
smaeung2@TMC02CN660MD6R online-boutique % kubectl -n online-boutique logs -l app=frontend -c istio-proxy
[2021-06-19T05:58:13.405Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 1 1 "-" "grpc-go/1.22.0" "5bd26972-a658-9210-b180-fae943343271" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.407Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 20 19 1 1 "-" "grpc-go/1.22.0" "fa642397-bd8c-99e5-ad6b-bac46f9a24b8" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.409Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 1 1 "-" "grpc-go/1.22.0" "6dd96c2a-c959-9c1c-bea8-0d7b4d681dbe" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.411Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 1 1 "-" "grpc-go/1.22.0" "382dc765-2a8c-9fc7-9c36-c3fd1cd75818" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.413Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 26 19 1 1 "-" "grpc-go/1.22.0" "b15aab75-15e4-9050-a504-245df1d99f8a" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.415Z] "POST /hipstershop.CurrencyService/Convert HTTP/2" 200 - via_upstream - "-" 25 18 2 2 "-" "grpc-go/1.22.0" "c7e392ad-4843-9a0e-a031-755f2eba3520" "currencyservice:7000" "172.17.0.13:7000" outbound|7000||currencyservice.online-boutique.svc.cluster.local 172.17.0.11:59958 10.110.127.86:7000 172.17.0.11:44580 - default
[2021-06-19T05:58:13.419Z] "POST /hipstershop.AdService/GetAds HTTP/2" 200 - via_upstream - "-" 5 123 3 2 "-" "grpc-go/1.22.0" "0a353dee-e565-99bd-baf0-15e4fca731cf" "adservice:9555" "172.17.0.16:9555" outbound|9555||adservice.online-boutique.svc.cluster.local 172.17.0.11:37328 10.101.204.176:9555 172.17.0.11:40490 - default
[2021-06-19T05:58:13.389Z] "GET / HTTP/1.1" 200 - via_upstream - "-" 0 10647 34 33 "172.17.0.1" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36" "b34c6b91-5c99-99f5-aacd-0d15e0ccd9f3" "10.110.134.150" "172.17.0.11:8080" inbound|8080|| 127.0.0.6:53023 172.17.0.11:8080 172.17.0.1:0 outbound_.80_._.frontend.online-boutique.svc.cluster.local default
{"path":"/wrongpath","connection_termination_details":null,"requested_server_name":"outbound_.80_._.frontend.online-boutique.svc.cluster.local","request_id":"4ff03554-731e-9cc3-8d65-9ca11ffd20e1","upstream_service_time":"0","x_forwarded_for":"172.17.0.1","bytes_received":0,"response_code":404,"method":"GET","protocol":"HTTP/1.1","upstream_host":"172.17.0.11:8080","upstream_local_address":"127.0.0.6:51603","response_flags":"-","route_name":"default","start_time":"2021-06-19T06:04:55.075Z","bytes_sent":19,"response_code_details":"via_upstream","duration":1,"downstream_remote_address":"172.17.0.1:0","upstream_transport_failure_reason":null,"upstream_cluster":"inbound|8080||","user_agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36","downstream_local_address":"172.17.0.11:8080","authority":"10.110.134.150"}
{"upstream_local_address":"127.0.0.6:51603","connection_termination_details":null,"response_flags":"-","response_code":404,"upstream_transport_failure_reason":null,"upstream_cluster":"inbound|8080||","start_time":"2021-06-19T06:04:55.319Z","requested_server_name":"outbound_.80_._.frontend.online-boutique.svc.cluster.local","bytes_received":0,"protocol":"HTTP/1.1","route_name":"default","request_id":"1889c3ae-ba79-9044-b5c7-08b0b6d3270c","path":"/favicon.ico","response_code_details":"via_upstream","method":"GET","authority":"10.110.134.150","user_agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.106 Safari/537.36","x_forwarded_for":"172.17.0.1","upstream_service_time":"0","upstream_host":"172.17.0.11:8080","downstream_remote_address":"172.17.0.1:0","duration":1,"bytes_sent":19,"downstream_local_address":"172.17.0.11:8080"}
smaeung2@TMC02CN660MD6R online-boutique % 
