# 현서버 사양
  프로세서 : Intel Core(TM) i3-2100 CPU @3.1GHz <br>
  memory : 8.00GB <br>
  OS : Windows 10 Pro 64bit <br>
  Server 운영프로그램 : 아파치 <br>

## 다중서버 운영

  -. 공유기부분 별도 찾아보시길 <br>
  -. Apache24/conf/httpd.cfg의 내용중, Listen 항목을 찾아 Listen xxxx와 같은 방식으로 포트를 추가한다.<br>
  -. Apache24/conf/extra/httpd-vho0sts.cfg의 아래오 같은 항목을 추가시킨다.<br>
  예시)
  ```
  <VirtualHost *:xxxx>
      ServerAdmin webmaster@dummy-host.example.com
      DocumentRoot "(path~~)"
      ServerName dummy-host.example.com
      ServerAlias www.dummy-host.example.com
      ErrorLog "logs/dummy-host.example.com-error.log"
      CustomLog "logs/dummy-host.example.com-access.log" common
  </VirtualHost>
```
  -. 서버를 재실행한 후, 접속시 http:/~.com:xxxx로 접속.
