---
title: memcached
type: cache
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/cache/memcached.go
-->


Connects to a cluster of memcached services, a prefix can be specified to allow
multiple cache types to share a memcached cluster under different namespaces.


import Tabs from '@theme/Tabs';

<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

import TabItem from '@theme/TabItem';

<TabItem value="common">

```yaml
memcached:
  addresses:
  - localhost:11211
  prefix: ""
  ttl: 300
```

</TabItem>
<TabItem value="advanced">

```yaml
memcached:
  addresses:
  - localhost:11211
  prefix: ""
  ttl: 300
  retries: 3
  retry_period: 500ms
```

</TabItem>
</Tabs>

## Fields

### `addresses`

`array` A list of addresses of memcached servers to use.

### `prefix`

`string` An optional string to prefix item keys with in order to prevent collisions with similar services.

### `ttl`

`number` A TTL in seconds to set for items, after this period keys will be removed.

### `retries`

`number` The maximum number of retry attempts to make before abandoning a request.

### `retry_period`

`string` The duration to wait between retry attempts.

