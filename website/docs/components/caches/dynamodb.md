---
title: dynamodb
type: cache
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/cache/dynamodb.go
-->


Stores key/value pairs as a single document in a DynamoDB table. The key is
stored as a string value and used as the table hash key. The value is stored as
a binary value using the `data_key` field name.


import Tabs from '@theme/Tabs';

<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

import TabItem from '@theme/TabItem';

<TabItem value="common">

```yaml
dynamodb:
  table: ""
  hash_key: ""
  data_key: ""
  region: eu-west-1
```

</TabItem>
<TabItem value="advanced">

```yaml
dynamodb:
  table: ""
  hash_key: ""
  data_key: ""
  consistent_read: false
  ttl: ""
  ttl_key: ""
  region: eu-west-1
  endpoint: ""
  credentials:
    profile: ""
    id: ""
    secret: ""
    token: ""
    role: ""
    role_external_id: ""
  max_retries: 3
  backoff:
    initial_interval: 1s
    max_interval: 5s
    max_elapsed_time: 30s
```

</TabItem>
</Tabs>

A prefix can be specified to allow multiple cache types to share a single
DynamoDB table. An optional TTL duration (`ttl`) and field
(`ttl_key`) can be specified if the backing table has TTL enabled.

Strong read consistency can be enabled using the `consistent_read`
configuration field.

### Credentials

By default Benthos will use a shared credentials file when connecting to AWS
services. It's also possible to set them explicitly at the component level,
allowing you to transfer data across accounts. You can find out more
[in this document](/docs/guides/aws).

## Fields

### `table`

`string` The table to store items in.

### `hash_key`

`string` The key of the table column to store item keys within.

### `data_key`

`string` The key of the table column to store item values within.

### `consistent_read`

`bool` Whether to use strongly consistent reads on Get commands.

### `ttl`

`string` An optional TTL to set for items, calculated from the moment the item is cached.

### `ttl_key`

`string` The column key to place the TTL value within.

### `region`

`string` The AWS region to target.

### `endpoint`

`string` Allows you to specify a custom endpoint for the AWS API.

### `credentials`

`object` Optional manual configuration of AWS credentials to use. More information can be found [in this document](/docs/guides/aws).

### `credentials.profile`

`string` A profile from `~/.aws/credentials` to use.

### `credentials.id`

`string` The ID of credentials to use.

### `credentials.secret`

`string` The secret for the credentials being used.

### `credentials.token`

`string` The token for the credentials being used, required when using short term credentials.

### `credentials.role`

`string` A role ARN to assume.

### `credentials.role_external_id`

`string` An external ID to provide when assuming a role.

### `max_retries`

`number` The maximum number of retries before giving up on the request. If set to zero there is no discrete limit.

### `backoff`

`object` Control time intervals between retry attempts.

### `backoff.initial_interval`

`string` The initial period to wait between retry attempts.

### `backoff.max_interval`

`string` The maximum period to wait between retry attempts.

### `backoff.max_elapsed_time`

`string` The maximum period to wait before retry attempts are abandoned. If zero then no limit is used.


