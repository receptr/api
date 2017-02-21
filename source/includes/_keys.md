# Keys

## Get a Key

```http
GET /v2/keys/+16044401234/1 HTTP/1.1
Host: textsecure-service-ca.whispersystems.org:80
Connection: keep-alive
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36
X-Signal-Agent: OWD
Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Authorization: Basic KzEyMzQ1Njc4OTAxLjE6YWJjZGVmZytISUpLTE1OT1BXUlNUVQ==
Content-Type: application/json; charset=utf-8
Accept: */*
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,fr;q=0.6
```

```http
HTTP/1.1 200 OK
Date: Tue, 21 Feb 2017 01:04:12 GMT
Access-Control-Allow-Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Access-Control-Allow-Credentials: true
Access-Control-Expose-Headers:
Content-Type: application/json
Content-Encoding: gzip
Vary: Accept-Encoding
Content-Length: 326

{
  "identityKey": "ABC/123",
  "devices": [
    {
      "deviceId": 1,
      "registrationId": 123,
      "signedPreKey": {
        "keyId": 123,
        "publicKey": "123/ABC",
        "signature": "HELLO=="
      },
      "preKey": {
        "keyId": 123,
        "publicKey": "XYZ"
      }
    }
  ]
}
```

## Adding a Key

```http
PUT /v2/keys HTTP/1.1
Host: textsecure-service-ca.whispersystems.org:80
Connection: keep-alive
Content-Length: 7511
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36
X-Signal-Agent: OWD
Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Authorization: Basic KzEyMzQ1Njc4OTAxLjE6YWJjZGVmZytISUpLTE1OT1BXUlNUVQ==
Content-Type: application/json; charset=UTF-8
Accept: */*
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,fr;q=0.6

{
  "identityKey": "123/ABC",
  "signedPreKey": {
    "keyId": 1,
    "publicKey": "ABC+123",
    "signature": "ABC+123=="
  },
  "preKeys": [
    {
      "keyId": 1,
      "publicKey": "ABC+DEF+GHI"
    },
    {
      "keyId": "n",
      "publicKey": "..."
    },
    {
      "keyId": 100,
      "publicKey": "GHI+DEF+ABC"
    }
  ],
  "lastResortKey": {
    "keyId": 123,
    "publicKey": "ABC="
  }
}
```

```http
HTTP/1.1 204 No Content
Date: Tue, 21 Feb 2017 01:04:12 GMT
Access-Control-Allow-Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Access-Control-Allow-Credentials: true
Access-Control-Expose-Headers:
```

Used to add a new key. With the `preKeys`, there are 100 objects that will need to be accounted for.
Every one has an ID identifying where it is in the array.
