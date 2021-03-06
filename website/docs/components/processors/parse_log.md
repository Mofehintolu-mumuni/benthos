---
title: parse_log
type: processor
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/processor/parse_log.go
-->


Parses common log [formats](#formats) into [structured data](#codecs). This is
easier and often much faster than [`grok`](/docs/components/processors/grok).


import Tabs from '@theme/Tabs';

<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

import TabItem from '@theme/TabItem';

<TabItem value="common">

```yaml
parse_log:
  format: syslog_rfc5424
  codec: json
```

</TabItem>
<TabItem value="advanced">

```yaml
parse_log:
  format: syslog_rfc5424
  codec: json
  parts: []
```

</TabItem>
</Tabs>

## Fields

### `format`

`string` A common log [format](#formats) to parse.

Options are: `syslog_rfc5424`.

### `codec`

`string` Specifies the structured format to parse a log into.

Options are: `json`.

### `parts`

`array` An optional array of message indexes of a batch that the processor should apply to.
If left empty all messages are processed. This field is only applicable when
batching messages [at the input level](/docs/configuration/batching).

Indexes can be negative, and if so the part will be selected from the end
counting backwards starting from -1.

## Codecs

Currently the only supported structured data codec is `json`.

## Formats

### `syslog_rfc5424`

Makes a best effort to parses a log following the
[Syslog rfc5424](https://tools.ietf.org/html/rfc5424) spec. The resulting
structured document may contain any of the following fields:

- `message` (string)
- `timestamp` (string, RFC3339)
- `hostname` (string)
- `procid` (string)
- `appname` (string)
- `msgid` (string)
- `structureddata` (object)


