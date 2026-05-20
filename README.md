malvm@ai-server /mnt/raid/projects/ElplatAI $ sudo iptables -L DOCKER-CT -n -v
Chain DOCKER-CT (1 references)
 pkts bytes target     prot opt in     out     source               destination
 251K  858M ACCEPT     all  --  *      docker0  0.0.0.0/0            0.0.0.0/0            ctstate RELATED,ESTABLISHED
malvm@ai-server /mnt/raid/projects/ElplatAI $ sudo iptables -L DOCKER-CT -n -v
sudo iptables -L DOCKER-INTERNAL -n -v
sudo iptables -L DOCKER-BRIDGE -n -v
Chain DOCKER-CT (1 references)
 pkts bytes target     prot opt in     out     source               destination
 251K  858M ACCEPT     all  --  *      docker0  0.0.0.0/0            0.0.0.0/0            ctstate RELATED,ESTABLISHED
Chain DOCKER-INTERNAL (1 references)
 pkts bytes target     prot opt in     out     source               destination
Chain DOCKER-BRIDGE (1 references)
 pkts bytes target     prot opt in     out     source               destination
    0     0 DOCKER     all  --  *      docker0  0.0.0.0/0            0.0.0.0/0
malvm@ai-server /mnt/raid/projects/ElplatAI $ sudo iptables -L DOCKER-BRIDGE -n -v
Chain DOCKER-BRIDGE (1 references)
 pkts bytes target     prot opt in     out     source               destination
    0     0 DOCKER     all  --  *      docker0  0.0.0.0/0            0.0.0.0/0
malvm@ai-server /mnt/raid/projects/ElplatAI $
