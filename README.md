# K8S

A simple example of an architecture in EKS.

### Prerequisites

* Install the ekstl tool https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html
* Install the helm tool https://helm.sh/docs/intro/using_helm/

Please read about these two tools:
* https://helm.sh/docs/intro/using_helm/
* https://eksctl.io/

### How does it work

The following architecture consisting of two applications. The first application displays a static web page and the second application communicates with a redis database to store information.

Below is a diagram of the architecture

<img src="./resources/k8s.png" title="Architecture">
## Deployment

The cluster must be created with the following command, be sure to rename the resource in the file.
```
eksctl create cluster -f ekscluster.yaml
```
you must enter the app-chart folder and run the following command to download the project dependencies.
```
helm dependency update
```
Finally run the following command to deploy all resources
```
helm install . --generate-name
```
If you have kubectl installed you can get the load balancer endpoint to see the application working with the following command.
```
kubectl describe ing
```


## Authors

* **Luis Sic** - *TT* - [Sluis](https://github.com/LuisSic)


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Trambo Cloud
