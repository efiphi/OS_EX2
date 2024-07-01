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






