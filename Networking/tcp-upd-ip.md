### Protocol

- Is a simple an agreed set of rules for how devices talk to each other.

- Different systems can talk to another one, because them follow the same rules.

- DevOps engineer should know: **TCP**, **UDP**, **IP**

### IP

- **Internet Protocol** works at the Network Layer.

- Make sure a packet data sent to the right destination.

- A device has an unique IP address -> **IP Protocol** uses it to move packet from this machine to another one.

### TCP

- **Transmission Control Protocol** is _connection-oriented_.

- 2 devices will "shake hands" before sending anything (hmm, maybe for authorization).

- Splits the bundle of data to many smaller packets -> numbers them -> wait the other side to **acknowledge** each packet.

> But, if a packet missed if transfer progress, what'll happen?
>
> **TCP** will resend it.

-> Machine B will receice the full data package sent by Machine A.

- TCP makes sure nothing lost, nothing scrambled.

-> Trade-off: a little extra overhead, delay.

### UDP

- Define another way to send data different from TCP.

- **User Datagram Protocol** is _connectionless_.

- No hand-shake, no acknowledge.

- Just addresses the data, fires it off.

-> It is very fast, but not guaranteed.
