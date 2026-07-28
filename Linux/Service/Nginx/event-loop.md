### Event Loop in Nginx

- Event Loop runs an infinity loop, if any socket has data -> process request -> move to another socket.

```
while (true) {

    check_socket

    process_request

    move to another socket

}
```
