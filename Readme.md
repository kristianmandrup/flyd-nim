# Nim bindings for FlydJS stream library

[Flyd](https://github.com/paldepind/flyd) is a popular choice with the [Meiosis pattern](https://meiosis.js.org/)

## API

See [Flyd API](https://github.com/paldepind/flyd#api)

```nim
# on stream instance
proc pipe*(stream: Stream, fn: proc(v: Stream): Stream): Stream
proc map*(stream: Stream, fn: proc(v: Stream): Stream): Stream
proc of*(value: auto): Stream

# global static methods
proc stream*(value: auto): Stream
proc combine*(combiner: proc(streams: varargs[auto]: auto), dependencies: auto): Stream
proc isStream*(stream: Stream): bool
proc immediate*(stream: Stream): Stream
proc endsOn*(endStream: Stream, stream: Stream): Stream
proc map*(fn: proc(value: auto): auto, stream: Stream): Stream
proc chain*(fn: proc(value: auto): Stream, stream: Stream): Stream
proc apply*(valueStream: Stream, functionStream: Stream): Stream
proc on*(fn: proc(value: auto): auto, stream: Stream): auto
proc scan*(fn: proc(value: auto): auto, acc: auto, stream: Stream): auto
proc merge*(stream1: Stream, stream2: Stream): Stream
proc transduce*(transduer: proc(value: auto): auto, stream: Stream): Stream
proc curryN*(number: cint, fn: proc(value: auto): auto): auto
```
