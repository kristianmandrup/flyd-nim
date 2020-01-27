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
proc stream*(value: auto): Stream {.
importcpp: "flyd.stream(#)".}
proc combine*(combiner: proc(streams: varargs[auto]: auto), dependencies: auto): Stream {.
importcpp: "flyd.stream(#)".}
proc isStream*(stream: Stream): bool {.
importcpp: "flyd.isStream(#)".}
proc immediate*(stream: Stream): Stream {.
importcpp: "flyd.immediate(#)".}
proc endsOn*(endStream: Stream, stream: Stream): Stream {.
importcpp: "flyd.immediate(#)".}
proc map*(fn: proc(value: auto): auto, stream: Stream): Stream {.
importcpp: "flyd.map(#)".}
proc chain*(fn: proc(value: auto): Stream, stream: Stream): Stream {.
importcpp: "flyd.chain(#)".}
proc apply*(valueStream: Stream, functionStream: Stream): Stream {.
importcpp: "flyd.ap(#)".}
proc on*(fn: proc(value: auto): auto, stream: Stream): auto {.
importcpp: "flyd.on(#)".}
proc scan*(fn: proc(value: auto): auto, acc: auto, stream: Stream): auto {.
importcpp: "flyd.scan(#)".}
proc merge*(stream1: Stream, stream2: Stream): Stream {.importcpp: "flyd.merge(#)".}
proc transduce*(transduer: proc(value: auto): auto, stream: Stream): Stream {.importcpp: "flyd.transduce(#)".}
proc curryN*(number: cint, fn: proc(value: auto): auto): auto
```
