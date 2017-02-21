# Devices

## List Devices

```http
GET /v1/devices HTTP/1.1
Host: textsecure-service-ca.whispersystems.org:80
Connection: keep-alive
Cache-Control: max-age=0
Authorization: Basic KzEyMzQ1Njc4OTAxLjE6YWJjZGVmZytISUpLTE1OT1BXUlNUVQ==
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,fr;q=0.6
```

```http
HTTP/1.1 200 OK
Date: Tue, 21 Feb 2017 01:49:28 GMT
Content-Type: application/json
Content-Length: 164

{
  "devices": [
    {
      "id": 1,
      "name": null,
      "lastSeen": 1487635200000,
      "created": 1468536627499
    },
    {
      "id": 2,
      "name": "Chrome on Mac",
      "lastSeen": 1487635200000,
      "created": 1487639050612
    }
  ]
}
```

Lists all of the devices that a user owns.
The first one will most likely be the device that the user owns.
The second one is their desktop application.

## Adding a Device

```http
PUT /v1/devices/148824 HTTP/1.1
Host: textsecure-service-ca.whispersystems.org:80
Connection: keep-alive
Content-Length: 180
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36
X-Signal-Agent: OWD
Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Authorization: Basic KzEyMzQ1Njc4OTAxLjE6YWJjZGVmZytISUpLTE1OT1BXUlNUVQ==
Content-Type: application/json; charset=UTF-8
Accept: */*
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,fr;q=0.6

{
  "signalingKey": "123abc==",
  "supportsSms": false,
  "fetchesMessages": true,
  "registrationId": 123,
  "name": "Chrome on Mac"
}
```

```http
HTTP/1.1 200 OK
Date: Tue, 21 Feb 2017 01:04:10 GMT
Access-Control-Allow-Origin: chrome-extension://bikioccmkafdpakkkcpdbppfkghcmihk
Access-Control-Allow-Credentials: true
Access-Control-Expose-Headers:
Content-Type: application/json
Content-Length: 14

{
  "deviceId": 2
}
```

This is used to add a new device from the response in provisioning a new device.
