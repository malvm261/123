malvm@ai-server /mnt/raid/projects/ElplatAI $ sudo iptables -L DOCKER-USER -n -v
Chain DOCKER-USER (1 references)
 pkts bytes target     prot opt in     out     source               destination
malvm@ai-server /mnt/raid/projects/ElplatAI $ sudo iptables -L DOCKER-FORWARD -n -v
Chain DOCKER-FORWARD (1 references)
 pkts bytes target     prot opt in     out     source               destination
 413K  867M DOCKER-CT  all  --  *      *       0.0.0.0/0            0.0.0.0/0
 162K 8986K DOCKER-INTERNAL  all  --  *      *       0.0.0.0/0            0.0.0.0/0
 162K 8986K DOCKER-BRIDGE  all  --  *      *       0.0.0.0/0            0.0.0.0/0
 162K 8986K ACCEPT     all  --  docker0 *       0.0.0.0/0            0.0.0.0/0
malvm@ai-server /mnt/raid/projects/ElplatAI $
