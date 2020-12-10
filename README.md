# Sample demo

To reproduce, run the app.

Check the log level for `com.example`:

```
$ curl 'http://localhost:8080/actuator/loggers/com.example' -i -X GET

```               

```

HTTP/1.1 200
Content-Disposition: inline;filename=f.txt
Content-Type: application/vnd.spring-boot.actuator.v3+json
Transfer-Encoding: chunked
Date: Thu, 10 Dec 2020 09:02:45 GMT

{"configuredLevel":"DEBUG","effectiveLevel":"DEBUG"}%
```                                                  

Clear the log level:

```
$ curl 'http://localhost:8080/actuator/loggers/com.example' -i -X POST -H 'Content-Type: application/json' -d '{}' 
```          

Get the log level again yield:

```

HTTP/1.1 200
Content-Disposition: inline;filename=f.txt
Content-Type: application/vnd.spring-boot.actuator.v3+json
Transfer-Encoding: chunked
Date: Thu, 10 Dec 2020 09:03:53 GMT

{"configuredLevel":"INFO","effectiveLevel":"INFO"}
```