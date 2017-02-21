# Websocket

## Login

```http
GET wss://textsecure-service-ca.whispersystems.org:80/v1/websocket/?login=%2B12345678901.1&password=abcdefg+HIJKLMNOPWRSTU&agent=OWD HTTP/1.1
Host: textsecure-service-ca.whispersystems.org:80
Connection: Upgrade
Pragma: no-cache
Cache-Control: no-cache
Upgrade: websocket
Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Sec-WebSocket-Version: 13
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/55.0.2883.95 Safari/537.36
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,fr;q=0.6
Sec-WebSocket-Key: ZW5jcnlwdGVk==
Sec-WebSocket-Extensions: permessage-deflate; client_max_window_bits
```

```http
HTTP/1.1 101 Switching Protocols
Date: Fri, 03 Feb 2017 03:05:57 GMT
Connection: Upgrade
Sec-WebSocket-Accept: ZW5jcnlwdGVk==
Upgrade: WebSocket
```

## Provisioning

This is the request used when you want to register a new device.
Signal asks for your phone to scan a QR code, which then sends the response back to the app saying you've registered.

```http
GET wss://textsecure-service-ca.whispersystems.org:80/v1/websocket/provisioning/?agent=OWD HTTP/1.1
Host: textsecure-service-ca.whispersystems.org:80
Connection: Upgrade
Pragma: no-cache
Cache-Control: no-cache
Upgrade: websocket
Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Sec-WebSocket-Version: 13
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,fr;q=0.6
Sec-WebSocket-Key: ZW5jcnlwdGVk==
Sec-WebSocket-Extensions: permessage-deflate; client_max_window_bits
```

```http
HTTP/1.1 101 Switching Protocols
Date: Tue, 21 Feb 2017 00:59:57 GMT
Connection: Upgrade
Sec-WebSocket-Accept: ZW5jcnlwdGVk==
Upgrade: WebSocket
```