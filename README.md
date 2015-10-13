# GO_REUSEPORT

**GO_REUSEPORT** is a little package to create `net.TCPListener` and `net.UDPConn` objects that support the [SO_REUSEPORT](http://lwn.net/Articles/542629/) socket option. This allows multiple daemons to listen on the same port, which opens some interesting possibilities.

The golang net package does not support setting socket options so this is not possible by default. This package works by using system calls to manually create the socket and set the desired options. The file descriptor that this process returns can then be turned into `net.FileListener` and `net.FileConn` objects using `net.FileListener` and `net.FileConn`, respectively.


## TODO

* Add Example

* Add More documentation

* Update test code to handle new functionality

* Test on other platforms other than Linux

## Thanks

Forked from [kavu/go_reuseport](https://github.com/kavu/go_reuseport)
Inspired by [Artur Siekielski](https://github.com/aartur) [post](http://freeprogrammersblog.vhex.net/post/linux-39-introdued-new-way-of-writing-socket-servers/2) about `SO_REUSEPORT`.
