# k8s-iperf

## Deploy Cluster
```
This requires a kubernetes cluster. Pleae have a kubernetes cluster available to run this on
```

## Deploy iperf
### Before you begin
* Designate one of the nodes to run the iperf-server
```
kubectl label node <node_name> iperf-server=true
```

* To test all the nodes
```
git clone https://github.com/satchpx/k8s-iperf
cd k8s-iperf/
./run
```

* Example Output
```

```

* To test a specific node
```
git clone https://github.com/satchpx/k8s-iperf
cd k8s-iperf/
kubectl apply -f k8s-iperf.yaml
kubectl get pods -o wide
# Get the pod running on the node under test
kubectl exec <pod> -- iperf3 -c iperf-server
```