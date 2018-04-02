# Firebase authentication with ASP.NET Core sample

The project defines one controller called `SampleController` with two endpoints:

 - `/api/sample/public`: accessible without any authentication
 - `/api/sample/protected`: only accessible if a correct OAuth token is provided

We can access the public endpoint with a simple `GET` request without any token:

```
GET http://localhost:5000/api/sample/public HTTP/1.1
```

And we get

```
HTTP/1.1 200 OK
```

However, if we try to reach the second endpoint without a token:

```
GET http://localhost:5000/api/sample/protected HTTP/1.1
```

We get

```
HTTP/1.1 401 Unauthorized
```

In order to access the protected endpoint, we need to provide the OAuth token in the `Authorization` header:

```
GET http://localhost:5000/api/sample/protected HTTP/1.1
Authorization: Bearer [OAUTH_TOKEN]
```
