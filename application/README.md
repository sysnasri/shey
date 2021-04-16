### Application

You can see 4 different versions of applications exist in `.` folder. The API of application is exposed on port `3000` and currently there are two endpoints implemented:

* `GET /`: prints welcome message with application version
* `GET /healthz`: responds the request with `200` if application is healthy and `500` if it's not.


