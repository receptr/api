# Attachments

## List Attachments

```http
GET /v1/attachments HTTP/1.1
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
Date: Tue, 21 Feb 2017 01:47:57 GMT
Content-Type: application/json
Content-Length: 218

{
  "id":123456789,
  "location":"https://whispersystems-textsecure-attachments.s3.amazonaws.com/123456789?AWSAccessKeyId=123&Expires=123&Signature=ABC"
}
```

Not sure what this does, but it appears to provide a single attachment object.

## Show an Attachment

```http
GET /v1/attachments/123456789 HTTP/1.1
Host: textsecure-service-ca.whispersystems.org:80
Connection: keep-alive
Authorization: Basic KzEyMzQ1Njc4OTAxLjE6YWJjZGVmZytISUpLTE1OT1BXUlNUVQ==
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,fr;q=0.6
```

```http
HTTP/1.1 200 OK
Date: Tue, 21 Feb 2017 01:44:18 GMT
Content-Type: application/json
Content-Length: 195

{
  "location":"https://whispersystems-textsecure-attachments.s3.amazonaws.com/123456789?AWSAccessKeyId=123&Expires=123&Signature=ABC"
}
```

Provides a location to an AWS attachment.
If you'd like to view the attachment that is responded in the location field, make sure you set your `Content-Type` to `application/octet-stream`.
