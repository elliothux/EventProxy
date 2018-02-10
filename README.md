# A ease-to-use event proxy within 1KB

## Install
`npm install event-proxy.js`

## Basic Usage

```js
import EventProxy from 'event-proxy.js';
const event = new EventProxy();

const sayHello = (name) => console.log(`Hello ${name}`);
event.on('hello', sayHello);
event.emit('hello', 'Joe');     // Log "Hello Joe"
event.cancel('hello', sayHello);
event.emit('hello', 'Joe');     // Nothing Happened

event.once('hello', sayHello);
event.emit('hello', 'Joe');     // Log "Hello Joe"
event.emit('hello', 'Joe');     // Nothing Happened
```

## API

* **on(eventName, handler)**: Add an event Listener
* **once(eventName, handler)**: Add a disposable event Listener
* **emit(eventName, [...args])**: Trigger an event
* **cancel(eventName, handler)**: Remove the handler of the event
* **cancelOnce(eventName, handler)**: Remove the disposable handler of the event
* **cancelAll(eventName)**: Remove all handlers of the event
* **cancelAllOnce(eventName)**: Remove all disposable handlers of the event
