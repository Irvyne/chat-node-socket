# Chat using Node/Express ~~and React~~ (Redis)

## Intro

A small real time chat build with Node/Express using Redis.

**Redis** is required (storage of users and messages, IP included).

## Installation

`yarn install` to install dependencies.

Run node server with `yarn start` and follow instructions (server run on [http://localhost:3000](http://localhost:3000))

## API

## Connection and other Events

`client` will emit some events about the state of the connection to the Redis server.

### Receive

Open socket on client side.

```js
let socket = io();
```

#### chat.join (receive)

* **username** is mandatory (any valid string)

```js
socket.emit('chat.join', username);
```

#### chat.message (receive)

* **message** is mandatory (any valid string)

```js
socket.emit('chat.message', message);
```

### Emit

#### chat.join (emit)

```json
{
  "username": "John DOE"
}
```

#### chat.message (emit)

```json
{
  "username": "John DOE",
  "message": "Lorem Ipsum"
}
```

#### chat.disconnect (emit)

```json
{
  "username": "John DOE"
}
```
