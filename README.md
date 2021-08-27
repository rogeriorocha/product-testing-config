# About
Sample REST API in ***golang***.

## Requirements:
- [Skaffold](https://skaffold.dev/) - Local Kubernetes Development
- [Kubernetes Cluster](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) (eg [k3d](https://k3d.io/) local cluster)
- [Docker](https://www.docker.com/) - Container
- kubectl CLI




## services
* ***api*** REST;
* ***mySql*** database.
 
### Start Skaffold deploy
```shell=
skaffold dev --port-forward  --trigger polling
```

### methods

* Set API_URL
```shell=
export API_URL="http://localhost:8080/api/v1/products"
```

* ***get*** ALL products
```shell=
curl $API_URL
```

* ***post*** add one product
```shell=
curl $API_URL \
    --include \
    --header "Content-Type: application/json" \
    --request "POST" \
    --data '{"id": "1","name": "bike","value": 4009.99}'

curl $API_URL \
    --include \
    --header "Content-Type: application/json" \
    --request "POST" \
    --data '{"id": "2","name": "ebook x","value": 5.00}'

curl $API_URL \
    --include \
    --header "Content-Type: application/json" \
    --request "POST" \
    --data '{"id": "3","name": "Server z","value": 90000.00}'
````
* ***get*** ONE product
```shell=
curl $API_URL/1

````
* ***put*** change ONE product
```shell=
curl $API_URL/1 \
    --include \
    --header "Content-Type: application/json" \
    --request "PUT" \
    --data '{"value": 11500.99}'    
````
* ***delete*** ONE product
```shell=
curl $API_URL/1 \
    --include \
    --header "Content-Type: application/json" \
    --request "DELETE"
    
```
