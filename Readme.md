Question 1: 
1
4
9
1
2
4
6
1
2
3
6
7
8
9
This is what outputted when I did the sequence 3 times. When the loss was
introduced, UDP became unreliable. Several numbers from the sequence were
missing. This occurred because UDP is a connectionless protocol that does not
provide acknowledgements, retransmissions, or ordering guarantees. When packets
were lost due to simulated network loss, UDP did not attempt to recover them,
resulting in incomplete data delivery


Question 2:
When the loss was introduced, TCP stayed reliable and in order (no numbers
skipped). However, the speed of the communication decreased, with delays and 
even occasional stalls before data was delivered. In some cases, the connection
seemed to hang or terminate before completing the full sequence. This is becauseTCP uses acknowledgements and retransmissions to guarantee reliable delivery.
Under high loss, TCP must repeatedly retransmit lost packages and reduce its
congestion window, which increases latency and can lead to timeouts or stalled 
connections.
