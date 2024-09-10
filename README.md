# k8s-minikube-demo

This repo is for testing minikube locally using the Demo Project provided by "TechWorld with Nana" as explained in [THIS VIDEO](https://www.youtube.com/watch?v=s_o8dwzRlu4&ab_channel=TechWorldwithNana)

Notes: 

I was following your tutorial on macOS Ventura with Docker Desktop v4.17 and it seems that Docker changed the way it integrates with host's network. What you shown will still work on Linux where Docker adds a new interface to the host OS through which you can communicate with containers. In my case, host OS had no clue how to find the k8s server with the IP returned by `minikube ip`, there was no routing information in the routing table.

What you have to do is to run `minikube service webapp-service` which will create a tunnel to the service via ports published by minikube container and redirect the browser to tunneled port.