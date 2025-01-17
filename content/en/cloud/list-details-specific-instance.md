---
title: "How do I retrieve the details of an instance from a command line?"
type: docs
tags:
- API
---

You can retrieve the details of an instance from a command line using the
[Cloud API](https://cloud.lambdalabs.com/api/v1/docs).

First, [generate an API key](https://cloud.lambdalabs.com/api-keys). Then, run
the following command:

```bash
curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/instances/INSTANCE-ID | jq .
```

Replace **API-KEY** with your actual API key. **Don't remove the trailing
colon (:).**

Replace **INSTANCE-ID** with the ID of the instance you want details about.

{{% alert title="Note" color="info" %}}
[Use the API to obtain the IDs of your instances]({{< relref "list-running-instances" >}}).
{{% /alert %}}
