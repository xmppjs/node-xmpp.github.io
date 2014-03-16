---
layout: page
title: "node-xmpp-client"
category: doc
date: 2014-03-15 21:07:32
---

* Name: __node-xmpp-client__
* NPM package name: __node-xmpp-client__
* Source: __https://github.com/node-xmpp/node-xmpp-client_-

```
var Client = require('node-xmpp-client')
var client = new Client(...parameters...)
```

### Parameters

* __jid__ [String]: The jid of the user you wish to log in as. If no _host_ parameter provided an SRV lookup will be performed on the domain (where possible).
* __password__ [String]: Password to be used for login
* __host__ [String]: The host where the the XMPP server is located
* __preferred__ [String]: The preferred SASL mechanism to use for authentication
* __boshURL__ [String]: A BOSH URL endpoint to use (used in preference to a socket if provided)
* __websocketsURL__ [String]: A websocket URL endpoint to use (used in preference to a socket and BOSH endpoint if provided)
* __register__ [Boolean]: Create a new account on the server
* __port__ [Int]: Port number to use for socket connection
* __reconnect__ [Boolean]: Reconnect on disconnection
* __legacySSL__ [Boolean]: Connect to the legacy SSL port (5223) - requires at least the _host_ to be specified
* __credentials__ [Boolean]: TLS or SSL key and certificate credentials
* __actAs__ [String]: if admin user act on behalf of another user
* __disallowTLS__ [Boolean]: Prevent upgrading of the connection to a secure one using TLS
* __oauth2_token__ [String]: OAuth2 token e.g. used for logging into google talk
* __oauth2_auth__ [String]: OAuth2 namespace e.g. used for logging into google talk
* __api_key__ [String]: For logging into Facebook XMPP account
* __access_token__ [String]: For logging into Facebook XMPP account

# Basic Example

```
var Client = require('node-xmpp-client')

var client = new Client({
    jid: 'user@example.com',
    password: 'password'
})

client.on('online', function() {
    console.log('online')
})

client.on('stanza', function(stanza) {
    console.log('Incoming stanza: ', stanza.toString())
})
```

# Closing a connection

```
client.end()
```