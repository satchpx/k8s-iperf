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
root@node1:~/k8s-iperf# ./run
deployment.apps/iperf-server created
service/iperf-server created
daemonset.apps/iperf-client created
Waiting for iperf server to start...
Waiting for iperf server to start...
Waiting for iperf server to start...
Waiting for iperf server to start...
[INFO]: Server is running on 70.0.72.79
[INFO]: Waiting for clients to start...
Client on 70.0.72.79:  Connecting to host iperf-server, port 5201
Client on 70.0.72.79:  [  4] local 10.233.102.190 port 54238 connected to 10.233.1.227 port 5201
Client on 70.0.72.79:  [ ID] Interval           Transfer     Bandwidth       Retr  Cwnd
Client on 70.0.72.79:  [  4]   0.00-1.00   sec  1.86 GBytes  15.9 Gbits/sec  941    779 KBytes
Client on 70.0.72.79:  [  4]   1.00-2.00   sec  1.88 GBytes  16.1 Gbits/sec  126    898 KBytes
Client on 70.0.72.79:  [  4]   2.00-3.00   sec  2.04 GBytes  17.5 Gbits/sec   38    898 KBytes
Client on 70.0.72.79:  [  4]   3.00-4.00   sec  2.04 GBytes  17.5 Gbits/sec   45    898 KBytes
Client on 70.0.72.79:  [  4]   4.00-5.00   sec  2.01 GBytes  17.2 Gbits/sec  187    918 KBytes
Client on 70.0.72.79:  [  4]   5.00-6.00   sec  2.04 GBytes  17.6 Gbits/sec   24    930 KBytes
Client on 70.0.72.79:  [  4]   6.00-7.00   sec  1.98 GBytes  17.0 Gbits/sec  911    658 KBytes
Client on 70.0.72.79:  [  4]   7.00-8.00   sec  2.00 GBytes  17.2 Gbits/sec   34    673 KBytes
Client on 70.0.72.79:  [  4]   8.00-9.00   sec  2.03 GBytes  17.4 Gbits/sec  193    745 KBytes
Client on 70.0.72.79:  [  4]   9.00-10.00  sec  2.07 GBytes  17.8 Gbits/sec   46    817 KBytes
Client on 70.0.72.79:  - - - - - - - - - - - - - - - - - - - - - - - - -
Client on 70.0.72.79:  [ ID] Interval           Transfer     Bandwidth       Retr
Client on 70.0.72.79:  [  4]   0.00-10.00  sec  19.9 GBytes  17.1 Gbits/sec  2545             sender
Client on 70.0.72.79:  [  4]   0.00-10.00  sec  19.9 GBytes  17.1 Gbits/sec                  receiver
Client on 70.0.72.79:
Client on 70.0.72.79:  iperf Done.

Client on 70.0.72.82:  Connecting to host iperf-server, port 5201
Client on 70.0.72.82:  [  4] local 10.233.75.4 port 59306 connected to 10.233.1.227 port 5201
Client on 70.0.72.82:  [ ID] Interval           Transfer     Bandwidth       Retr  Cwnd
Client on 70.0.72.82:  [  4]   0.00-1.00   sec   374 MBytes  3.13 Gbits/sec  481    338 KBytes
Client on 70.0.72.82:  [  4]   1.00-2.00   sec   315 MBytes  2.64 Gbits/sec  142    465 KBytes
Client on 70.0.72.82:  [  4]   2.00-3.00   sec   339 MBytes  2.84 Gbits/sec  204    342 KBytes
Client on 70.0.72.82:  [  4]   3.00-4.00   sec   308 MBytes  2.58 Gbits/sec   46    502 KBytes
Client on 70.0.72.82:  [  4]   4.00-5.00   sec   335 MBytes  2.81 Gbits/sec  215    422 KBytes
Client on 70.0.72.82:  [  4]   5.00-6.00   sec   326 MBytes  2.74 Gbits/sec  334    373 KBytes
Client on 70.0.72.82:  [  4]   6.00-7.00   sec   334 MBytes  2.80 Gbits/sec  154    422 KBytes
Client on 70.0.72.82:  [  4]   7.00-8.00   sec   284 MBytes  2.38 Gbits/sec  237    346 KBytes
Client on 70.0.72.82:  [  4]   8.00-9.00   sec   302 MBytes  2.54 Gbits/sec  307    472 KBytes
Client on 70.0.72.82:  [  4]   9.00-10.00  sec   284 MBytes  2.38 Gbits/sec  222    427 KBytes
Client on 70.0.72.82:  - - - - - - - - - - - - - - - - - - - - - - - - -
Client on 70.0.72.82:  [ ID] Interval           Transfer     Bandwidth       Retr
Client on 70.0.72.82:  [  4]   0.00-10.00  sec  3.12 GBytes  2.68 Gbits/sec  2342             sender
Client on 70.0.72.82:  [  4]   0.00-10.00  sec  3.12 GBytes  2.68 Gbits/sec                  receiver
Client on 70.0.72.82:
Client on 70.0.72.82:  iperf Done.

Client on 70.0.72.78:  Connecting to host iperf-server, port 5201
Client on 70.0.72.78:  [  4] local 10.233.71.42 port 48352 connected to 10.233.2.255 port 5201
Client on 70.0.72.78:  [ ID] Interval           Transfer     Bandwidth       Retr  Cwnd
Client on 70.0.72.78:  [  4]   0.00-1.00   sec   343 MBytes  2.87 Gbits/sec  208    373 KBytes
Client on 70.0.72.78:  [  4]   1.00-2.00   sec   273 MBytes  2.29 Gbits/sec  164    415 KBytes
Client on 70.0.72.78:  [  4]   2.00-3.00   sec   282 MBytes  2.36 Gbits/sec  145    481 KBytes
Client on 70.0.72.78:  [  4]   3.00-4.00   sec   291 MBytes  2.44 Gbits/sec  161    515 KBytes
Client on 70.0.72.78:  [  4]   4.00-5.00   sec   268 MBytes  2.25 Gbits/sec  293    588 KBytes
Client on 70.0.72.78:  [  4]   5.00-6.00   sec   271 MBytes  2.27 Gbits/sec  126    424 KBytes
Client on 70.0.72.78:  [  4]   6.00-7.00   sec   248 MBytes  2.08 Gbits/sec  244    394 KBytes
Client on 70.0.72.78:  [  4]   7.00-8.00   sec   292 MBytes  2.45 Gbits/sec   73    544 KBytes
Client on 70.0.72.78:  [  4]   8.00-9.00   sec   282 MBytes  2.37 Gbits/sec  156    396 KBytes
Client on 70.0.72.78:  [  4]   9.00-10.00  sec   215 MBytes  1.80 Gbits/sec  106    346 KBytes
Client on 70.0.72.78:  - - - - - - - - - - - - - - - - - - - - - - - - -
Client on 70.0.72.78:  [ ID] Interval           Transfer     Bandwidth       Retr
Client on 70.0.72.78:  [  4]   0.00-10.00  sec  2.70 GBytes  2.32 Gbits/sec  1676             sender
Client on 70.0.72.78:  [  4]   0.00-10.00  sec  2.70 GBytes  2.32 Gbits/sec                  receiver
Client on 70.0.72.78:
Client on 70.0.72.78:  iperf Done.

deployment.apps "iperf-server" deleted
service "iperf-server" deleted
daemonset.apps "iperf-client" deleted
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

### Troubleshoot
* If you run into issues...
```
kubectl apply -f k8s-iperf.yaml

# Make sure all the pods are running
./run
```