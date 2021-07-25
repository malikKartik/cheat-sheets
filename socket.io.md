## Socket.io cheatsheet
#### Sending to sender-client only
```socket.emit('message', "this is a test");```

#### Sending to all clients except sender
```socket.broadcast.emit('message', "this is a test");```

#### Sending to all clients in 'game' room(channel) except sender
```socket.broadcast.to('game').emit('message', 'nice game');```

#### Sending to sender client, only if they are in 'game' room(channel)
```socket.to('game').emit('message', 'enjoy the game');```

#### Sending to individual socketid
```socket.broadcast.to(socketid).emit('message', 'for your eyes only');```

#### Sending to all clients, include sender
```io.emit('message', "this is a test");```

#### Sending to all clients in 'game' room(channel), include sender
```io.in('game').emit('message', 'cool game');```

#### Sending to all clients in namespace 'myNamespace', include sender
```io.of('myNamespace').emit('message', 'gg');```

#### Send to all connected clients
```socket.emit();```

#### Send to all connected clients except the one that sent the message
```socket.broadcast.emit();```

#### Event listener, can be called on client to execute on server
```socket.on();```

#### For emiting to specific clients
```io.sockets.socket();```

#### Send to all connected clients (same as socket.emit)
```io.sockets.emit();```

#### Initial connection from a client.
```io.sockets.on();```

## Thanks to
[Kent Aguilar](https://stackoverflow.com/users/2814021/kent-aguilar) for his [answer](https://stackoverflow.com/questions/32674391/io-emit-vs-socket-emit) on Stack Overflow 
