Welcome to Node.js v20.12.2.
Type ".help" for more information.
> const express = require('express');
Uncaught Error: Cannot find module 'express'
Require stack:
- <repl>
    at Module._resolveFilename (node:internal/modules/cjs/loader:1143:15)
    at Module._load (node:internal/modules/cjs/loader:984:27)
    at Module.require (node:internal/modules/cjs/loader:1231:19)
    at require (node:internal/modules/helpers:179:18) {
  code: 'MODULE_NOT_FOUND',
  requireStack: [ '<repl>' ]
}
> const http = require('http');
undefined
> const socketIO = require('socket.io');
Uncaught Error: Cannot find module 'socket.io'
Require stack:
- <repl>
    at Module._resolveFilename (node:internal/modules/cjs/loader:1143:15)
    at Module._load (node:internal/modules/cjs/loader:984:27)
    at Module.require (node:internal/modules/cjs/loader:1231:19)
    at require (node:internal/modules/helpers:179:18) {
  code: 'MODULE_NOT_FOUND',
  requireStack: [ '<repl>' ]
}
>
> const PORT = process.env.PORT || 3000;
undefined
>
> const app = express();
Uncaught ReferenceError: express is not defined
> const server = http.createServer(app);
Uncaught ReferenceError: app is not defined
> const io = socketIO(server);
Uncaught ReferenceError: socketIO is not defined
>
> app.use(express.static(__dirname + '/public'));
Uncaught ReferenceError: app is not defined
>
> io.on('connection', (socket) => {
...   console.log('User connected');
...
...   // Menangani pergerakan pemain
...   socket.on('move', (data) => {
...     // Mengirim data pergerakan ke semua klien, termasuk pengirimnya
...     io.emit('move', data);
...   });
...
...   socket.on('disconnect', () => {
...     console.log('User disconnected');
...   });
... });
Uncaught ReferenceError: io is not defined
>
> server.listen(PORT, () => {
...   console.log(`Server running on port ${PORT}`);
... });
Uncaught ReferenceError: server is not defined
>
