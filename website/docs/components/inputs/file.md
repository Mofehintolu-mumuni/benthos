---
title: file
type: input
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/input/file.go
-->


Reads a file, where each line is processed as an individual message.

```yaml
input:
  file:
    path: ""
    multipart: false
    max_buffer: 1e+06
    delimiter: ""
```

## Fields

### `path`

`string` A path pointing to a file on disk.

### `multipart`

`bool` If set `true` each line is read as a message part, and an empty line
indicates the end of a message batch, and only then is the batch flushed
downstream.

### `max_buffer`

`number` Must be larger than the largest line of the target file.

### `delimiter`

`string` A string that indicates the end of a message within the target file. If left
empty then line feed (\n) is used.


