malvm@ai-server /mnt/raid/projects/ElplatAI $ sudo iptables -t nat -L -n -v
Пароль:
Chain PREROUTING (policy ACCEPT 186K packets, 18M bytes)
 pkts bytes target     prot opt in     out     source               destination
11030  662K DOCKER     all  --  *      *       0.0.0.0/0            0.0.0.0/0            ADDRTYPE match dst-type LOCAL

Chain INPUT (policy ACCEPT 145K packets, 15M bytes)
 pkts bytes target     prot opt in     out     source               destination

Chain OUTPUT (policy ACCEPT 332K packets, 20M bytes)
 pkts bytes target     prot opt in     out     source               destination
   68  4080 DOCKER     all  --  *      *       0.0.0.0/0           !127.0.0.0/8          ADDRTYPE match dst-type LOCAL

Chain POSTROUTING (policy ACCEPT 332K packets, 20M bytes)
 pkts bytes target     prot opt in     out     source               destination
 1593  104K MASQUERADE  all  --  *      !docker0  10.0.200.0/24        0.0.0.0/0

Chain DOCKER (2 references)
 pkts bytes target     prot opt in     out     source               destination
malvm@ai-server /mnt/raid/projects/ElplatAI $ sudo iptables -L -n -v | grep -E "80|DROP|REJECT"
Chain FORWARD (policy DROP 0 packets, 0 bytes)
    0     0 DROP       all  --  !docker0 docker0  0.0.0.0/0            0.0.0.0/0
malvm@ai-server /mnt/raid/projects/ElplatAI $ sudo iptables -L FORWARD -n -v
Chain FORWARD (policy DROP 0 packets, 0 bytes)
 pkts bytes target     prot opt in     out     source               destination
 413K  867M DOCKER-USER  all  --  *      *       0.0.0.0/0            0.0.0.0/0
 413K  867M DOCKER-FORWARD  all  --  *      *       0.0.0.0/0            0.0.0.0/0
malvm@ai-server /mnt/raid/projects/ElplatAI $
