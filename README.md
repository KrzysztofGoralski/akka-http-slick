http://www.lightbend.com/activator/template/akka-http-slick-guice

# akka-http-slick-guice

- akka-http : REST
- slick : database access & relational mapping
- guice: dependency injection

Forked from https://github.com/knoldus/akka-http-slick

Changes:
- Guice added
- Changed Routes to Get, Put, Post, Delete
- Changed urls
- Changed Json Parser from Lift to akka-http/Spray one
- Some fixes



### Run unit test:
```
$ ./activator test
 
 ```

### Run http server(It automatically connect with H2 database):
```
$ ./activator run

```

### Test http rest point using curl:

1) Get Bank detail by bank id

 request:
 ```
$ curl localhost:9000/bank/1
 
 ```
response:
```
 {"name":"SBI bank","id":1}
 ```

2)Get all Bank detail


 request:
```
$ curl localhost:9000/banks
```
response:
```
[{"name":"SBI bank","id":1},{"name":"PNB bank","id":2},{"name":"RBS bank","id":3}]
```

3)Save new bank detail

 request:
 ```
   $  curl -XPOST 'localhost:9000/bank'  -d '{"name":"New Bank"}'
   ```
   
 response:
 
 Bank has  been saved successfully

3)Update new bank detail

  request:
  ```
  $  curl -XPUT 'localhost:9000/bank'  -d '{"name":"Updated bank", "id":1}'
  
  ```
  
  response:
  
   Bank has  been updated successfully

4)delete bank by id

  request:
    
  ```
  $ curl -XDELETE 'localhost:9000/bank/1
  
  ```
  response:
  
  Bank has been deleted successfully
