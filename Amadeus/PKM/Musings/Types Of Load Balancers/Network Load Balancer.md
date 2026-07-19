# Network Load Balancer

An network load balancer provides high performance routing. They operate at the transport layer which lets them handle million of requests per second with ultra low latencies. To start routing traffic, it needs to be attached “[[Listeners|*listeners*]]” with a set of “[[Listeners|*rules*]]”.

Network load balancers cannot use [[Security Groups|security groups]], instead requests pass right through it to the [[Security Groups|security group]] of the resources.