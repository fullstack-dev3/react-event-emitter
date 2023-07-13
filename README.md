# react-event-emitter
Usage [Event Emitter](https://www.npmjs.com/package/eventemitter3) package in react app

## Introduction

#### - Define emitter service
```sh
import EventEmitter from 'eventemitter3';

const eventEmitter = new EventEmitter();

const Emitter = {
  on: (event, fn) => eventEmitter.on(event, fn),
  once: (event, fn) => eventEmitter.once(event, fn),
  off: (event, fn) => eventEmitter.off(event, fn),
  emit: (event, payload) => eventEmitter.emit(event, payload)
}

Object.freeze(Emitter);

export default Emitter;
```

#### - Listen the events from emitter service
```sh
componentDidMount() {
    // listens all the time
    Emitter.on('event_name', () => callback());

    // listens only to the first event
    Emitter.once('event_name', () => callback());
}

componentWillUnmount() {
    Emitter.off('event_name');
}
```

## Install
```sh
$ npm install
```

## Develop
```sh
$ npm start
```

## Production
```sh
$ npm build
