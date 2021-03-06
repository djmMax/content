---
alias: taesee4ua7
path: /docs/reference/simple-api/relation-aggregation
layout: REFERENCE
shorttitle: Relation Aggregation
description: For every available relation in your GraphQL schema, certain queries are automatically generated.
simple_relay_twin: fe1ahseek6
tags:
  - simple-api
  - queries
  - edges
  - relations
related:
  further:
  more:
---

# Relation Aggregation in the Simple API

Nodes connected to multiple nodes via a one-to-many or many-to-many edge expose the `_edgeMeta` field that can be used to query meta information of a connection rather than the actual connected nodes.

> Query meta information on all post nodes of a certain author node:

```graphql
---
endpoint: https://api.graph.cool/simple/v1/cixne4sn40c7m0122h8fabni1
disabled: false
---
query {
  User(id: "cixnekqnu2ify0134ekw4pox8") {
    id
    name
    _postsMeta {
      count
    }
  }
}
---
{
  "data": {
    "User": {
      "id": "cixnekqnu2ify0134ekw4pox8",
      "name": "John Doe",
      "_postsMeta": {
        "count": 3
      }
    }
  }
}
```

> Query meta information on certain post nodes of a certain author node:

```graphql
---
endpoint: https://api.graph.cool/simple/v1/cixne4sn40c7m0122h8fabni1
disabled: false
---
query {
  User(id: "cixnekqnu2ify0134ekw4pox8") {
    id
    name
    _postsMeta(filter: {
      title_contains: "adventure"
    }) {
      count
    }
  }
}
---
{
  "data": {
    "User": {
      "id": "cixnekqnu2ify0134ekw4pox8",
      "name": "John Doe",
      "_postsMeta": {
        "count": 1
      }
    }
  }
}
```
