---
tags:
  - project
  - project/integration_layer
---

## Decision

- `ris:Direction`  We are not Going to use Boilerplate. We are directly base Nest.js with base TypeORM.
- `ris:Direction` Inbound Request does not have to be Transformed and only the Response has to be transformed for Inbound -> Mirror Transformation

## Action Items

- Inbound Request Schema
```md
- incoming data
- service_id
- version
- ip
protocol
activity_type
req_type
user_agent
req_body
meta
after response
req_url
resp_body
transformed_resp_body
status
message
errors
has context menu
```
- Config 


