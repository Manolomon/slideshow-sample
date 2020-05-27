## Código Servidor

Se siguió el mismo criterio para la programación en Java Script del servidor, documentando de la siguiente forma:

```javascript
// Evento llamado por cliente al hacer un movimiento en su turno correspondiente
cliente.on("moverPieza", function(datos) {
  var movimiento = JSON.parse(datos);
  var stringmovimiento = JSON.stringify(movimiento);
  console.log("Movimiento pieza "+ movimiento['Ficha'] + " a la casilla " + movimiento['Casilla'] + " en el lobby " + movimiento['Lobby']);
  io.sockets.in(movimiento['Lobby']).emit("moverPiezaCliente", stringmovimiento); //codigo del lobby
});
```
