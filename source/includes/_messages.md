# Messages

```http
PUT /v1/messages/+16044408216 HTTP/1.1
Host: textsecure-service-ca.whispersystems.org:80
Connection: keep-alive
Content-Length: 402
Pragma: no-cache
Cache-Control: no-cache
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/55.0.2883.95 Safari/537.36
X-Signal-Agent: OWD
Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Authorization: Basic KzEyMzQ1Njc4OTAxLjE6YWJjZGVmZytISUpLTE1OT1BXUlNUVQ==
Content-Type: application/json; charset=UTF-8
Accept: */*
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,fr;q=0.6

{
  "messages": [
    {
      "type": 1,
      "destinationDeviceId": 1,
      "destinationRegistrationId": 1234,
      "body": "ZW5jcnlwdGVk=="
    }
  ],
  "timestamp": 1486087681922
}
```

```http
HTTP/1.1 200 OK
Access-Control-Allow-Credentials: true
Access-Control-Allow-Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Access-Control-Expose-Headers:
Content-Length: 19
Content-Type: application/json
Date: Fri, 03 Feb 2017 02:08:02 GMT

{
  "needSync": false
}
```
