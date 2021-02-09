# SagePay Administration API Client - Node.js

Enables management of sagepay admin and report panel through API.

## Overview

You need to read the API document here: [Customised reporting and admin API](https://www.sagepay.co.uk/support/find-an-integration-document/direct-integration-documents)

The API uses a tiny subset of XML syntax.

## Quick Start

```bash
npm install --save sagepay-admin-api-client
```

```javascript
const SagepayAdminApiClient = require("sagepay-admin-api-client");
const client = new SagepayAdminApiClient({
    user: "username",
    password: "password",
    vendor: "vendorname"
});
client.request({
    command: "version"
})
.then(res => {
    console.log(res);
    if (res.errorcode === '0000')
        console.log("Test connection succeed!");
    else
        console.log("Connection failed!");
});
```

### SagepayAdminApiClient

The class that provides access to the SagePay Administration and Reporting API.

### SagepayAdminApiClient.constructor

```javascript
const foo = new SagepayAdminApiClient(options);
```

Creates a new instance.

#### Parameters

* `options` Required, values to pass with the request.
* `options.endpoint` Optional, defaults to the **live** environment.
* `options.user` Required, passed as the `user` to the API.
* `options.password` Required, used to sign the requests.
* `options.vendor` Required, passed as the `vendor` to the API.
* `options.command` Required, command name to be run in SagePay Admin Panel.

If you want to play with sandbox, just set an environment variable like below and that's good to go.

```bash
export SAGEPAY_ENV='test'
```

### SagepayAdminApiClient.request

```
let foo = client.request(options);
```

Makes a request and returns a promise that resolves to the response.

## Licence

**MIT**
