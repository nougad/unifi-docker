# unifi-docker

Fork of https://github.com/jacobalberty/unifi-docker without health check

The HEALTHCHECK causes docker to write to disk every 30 seconds which prevents disk hibernation on NAS.

Example log in file `config.v2.json`:

    "Health": {
      "Status": "healthy",
      "FailingStreak": 0,
      "Log": [
        {
          "Start": "2019-10-04T16:42:07.855025309+02:00",
          "End": "2019-10-04T16:42:08.036342122+02:00",
          "ExitCode": 0,
          "Output": "HTTP/1.1 302 \r\nLocation: /manage\r\nTransfer-Encoding: chunked\r\nDate: Fri, 04 Oct 2019 14:42:07 GMT\r\n\r\nHTTP/1.1 302 \r\nLocation: /manage/account/login?redirect=%2Fmanage\r\nTransfer-Encoding: chunked\r\nDate: Fri, 04 Oct 2019 14:42:07 GMT\r\n\r\nHTTP/1.1 200 \r\nX-Frame-Options: SAMEORIGIN\r\nvary: accept-encoding\r\nAccept-Ranges: bytes\r\nLast-Modified: Tue, 17 Sep 2019 21:45:08 GMT\r\nCache-Control: max-age=0\r\nExpires: Fri, 04 Oct 2019 14:42:07 GMT\r\nContent-Type: text/html;charset=ISO-8859-1\r\nContent-Length: 12957\r\nDate: Fri, 04 Oct 2019 14:42:07 GMT\r\n\r\n"
        },
