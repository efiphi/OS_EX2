# OS_EX2

## OS_EX2_1

```bash
cd OS_EX2
make
cd OS_EX2_1
./ttt 123456789
```


## OS_EX2_2

```bash
cd OS_EX2_2
./mync -e "../OS_EX2_1/ttt 123456789"
```


## OS_EX2_3

### input case-

```bash
cd OS_EX2_3
./mync -e "../OS_EX2_1/ttt 123456789" TCPS 4050 -i
```
connect in another terminal
```bash
nc localhost 4050
```
provide moves on the second terminal, but view the result on the first terminal.


### both case-

```bash
cd OS_EX2_3
./mync -e "../OS_EX2_1/ttt 123456789" TCPS 4050 -b
```
connect in another terminal
```bash
nc localhost 4050
```
provide moves and view the result on the second terminal.


### output case-
first terminal
```bash
nc -l 4455
```
second terminal
```bash
cd OS_EX2_3
 ./mync -e "../OS_EX2_1/ttt 123456789" TCPS 4050 -o localhost 4455
```
third terminal
```bash
nc localhost 4050
```
provide moves on the third terminal, but view the result on the first terminal.


## OS_EX2_3.5
first terminal
```bash
cd OS_EX2_3.5
./mync TCPS 4050
```
second terminal
```bash
nc localhost 4050
```
third terminal
```bash
nc localhost 4050
```
now you can type a message in terminal 2 and see it on terminal 3, and the opposite.


## OS_EX2_4


start udp server and the output goes to the TCPClient at port 4455
```bash
./mync -e "./ttt 123456789" -i UDPS4050 -o TCPClocalhost,4455
```


send message to the server
```bash
echo "2" | nc -u localhost 4050
```

open a terminal and  get the message from the client
```
 nc -l 4455

```


## OS_EX2_6
### Example 1: Unix Domain Datagram Socket

 Server
```bash
./mync -i UDSSD/tmp/uds_socket -t 10
```


Client:
```bash
echo "Hello, World!" | ./mync -o UDSCD/tmp/uds_socket
```

### Example 2: Unix Domain Stream Socket

Server:

```bash

./mync -i UDSSS/tmp/uds_stream_socket -t 10
```

Client:

```
echo "Hello, World!" | ./mync -o UDSCS/tmp/uds_stream_socket
```








