nfs-rpc
=======

it's a copy of https://code.google.com/p/nfs-rpc/


Background
---------
Java app always need to call another java app,now we can use rmi/hessian etc. to realize,but they're not fast enough,so many of us select mina/netty or other high performance network framework to realize,every time when we change io framework,we need realize the rpc framework again,it's so boring....


Features
---------


Current
---------
This project abstract the high performance rpc framework,provide some basic implemenation:  

client proxy,so u can call remote just like call local: UserService.getById(id);  
server reflection,so u can intergrate the rpc framework with difference server implemenation,such as spring;  
server direct call,u can implement a specify interface to provide for client call;  
single or multi connections,in most case,single connection is enough,but in some cases,u'll need multi connections;  
connection reuse,so u don't need block user thread to wait for connection;  
synchronize call,rpc always need synchronize call;  
timeout,u cann't wait for server return response forever,so u need timeout policy,especially for online app;  
multi or custom serialize protocol(java/hessian/protobuf/kyro);  
custom your protocol.  

With above features,u can implement your high performance rpc framework quickly with your selected network framework. And the projects also provide mina/netty/grizzly implemenation,so u can directly use it to build your business,u can see here to find how to use it.

Future
---------
intergrate more network frameworks,such as thrift/avro;  
intergrate with aio;  
test coroutine version,maybe scala or kilim;  
server can use different threadpools to handle requests;  
support async call & group calls;  
add connection protect,avoid create connection again and again;  

more detail you can visit https://code.google.com/p/nfs-rpc/
