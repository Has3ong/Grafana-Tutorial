## How to install Graphite on Docker

```
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS


$ docker run -d --name graphite -p 81:81 -p 8125:8125/udp hopsoft/graphite-statsd
Unable to find image 'hopsoft/graphite-statsd:latest' locally
latest: Pulling from hopsoft/graphite-statsd
f069f1d21059: Pull complete
ecbeec5633cf: Pull complete
ea6f18256d63: Pull complete
54bde7b02897: Pull complete
a3ed95caeb02: Pull complete
ce9e695a6234: Pull complete
346026b9659b: Pull complete
3d46822e9c77: Pull complete
4b0f2eeceb8c: Pull complete
ad9da276fef3: Pull complete
d934de5f275c: Pull complete
e47fd90dedda: Pull complete
f48fe3a671fd: Pull complete
45d4f50330ff: Pull complete
88a5b2fbab59: Pull complete
ce6c96f9d88f: Pull complete
02ce5b92660a: Pull complete
23a63d46da04: Pull complete
cd23af556b69: Pull complete
eedc4aef4b64: Pull complete
8acbad64354e: Pull complete
4c699e959943: Pull complete
cff54fee7f53: Pull complete
7dfe00f307b9: Pull complete
52299f8acdf0: Pull complete
d135be430e8f: Pull complete
b9efd5692aee: Pull complete
c65bb89685f6: Pull complete
0126f89e61af: Pull complete
a17def4925ac: Pull complete
cf346fc58d14: Pull complete
57209780f97e: Pull complete
443c127f9f40: Pull complete
7d9b6f23cbd4: Pull complete
2c7c290c3500: Pull complete
ceba75fda696: Pull complete
b21f1aca3b6d: Pull complete
29cdcec60ded: Pull complete
b44a2d2bfccc: Pull complete
Digest: sha256:40d36394594e4d0a6d0497e6609c48b652b0a3e230b735dcd5b140fe76daacee
Status: Downloaded newer image for hopsoft/graphite-statsd:latest
b5237daa8036e3da98a7b0467fea7fd30f55f8ddc72ca6bb88de606a94e09edc

$ docker ps
CONTAINER ID        IMAGE                     COMMAND             CREATED             STATUS              PORTS                                                                                             NAMES
b5237daa8036        hopsoft/graphite-statsd   "/sbin/my_init"     2 seconds ago       Up 2 seconds        80/tcp, 2003-2004/tcp, 2023-2024/tcp, 8125-8126/tcp, 0.0.0.0:81->81/tcp, 0.0.0.0:8125->8125/udp   graphite
```

<img width=600 src="https://user-images.githubusercontent.com/44635266/64627224-338b6880-d42a-11e9-8565-a18185d42a3c.png">
