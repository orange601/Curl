# Curl을 사용해보자

# Curl 이란?
- cURL = Client URL
- 서버와 통신할 수 있는 커맨드 명령어툴. 오픈 소프트웨어.
- 다양한 프로토콜 지원 
- DICT, FILE, FTP, FTPS, Gopher, HTTP, HTTPS, IMAP, IMAPS, LDAP, LDAPS, POP3, POP3S, RTMP, RTSP, SCP, SFTP, SMB, SMBS, SMTP, SMTPS, Telnet, TFTP

# cURL 사용법
![24622445595e693512](https://user-images.githubusercontent.com/24876345/51222356-bda92d00-1980-11e9-8fa3-5cb3335226b3.png)



| short | long | 설명 | 비고 |
|:--------|:--------|--------|--------|
| _D | ```` --dump-header <file> ````| ```` <file> 에 HTTP header 를 기록한다.```` |   |
| -d | --data| HTTP Post data | FORM 을 POST 하는 HTTP나 JSON 으로 데이타를 주고받는 REST 기반의 웹서비스 디버깅시 유용한 옵션이다 |
| -J | --remote-header-name | 어떤 웹서비스는 파일 다운로드시 Content-Disposition Header 를 파싱해야 정확한 파일이름을 알 수 있을 경우가 있다. -J 옵션을 주면 헤더에 있는 파일 이름으로 저장한다. | curl 7.20 이상부터 추가된 옵션 |
| -k | --insecure | https 사이트를 SSL certificate 검증없이 연결한다. | wget 의 --no-check-certificate 과 비슷한 역할 수행 |
| -l | --head | HTTP header 만 보여주고 content 는 표시하지 않는다 | |
| -L | --location | 서버에서 HTTP 301 이나 HTTP 302 응답이 왔을 경우 redirection URL 로 따라간다. --max-redirs 뒤에 숫자로 redirection 을 몇 번 따라갈지 지정할 수 있다. 기본 값은 50이다 | curl -v daum.net 을 실행하면 결과값으로 다음과 같이 HTTP 302 가 리턴된다. ```` < HTTP/1.1 302 Object Moved  < Location: http://www.daum.net/ ```` -L 옵션을 추가하면 www.daum.net 으로 재접속하여 결과를 받아오게 된다. |
| -o | --output FILE | curl 은 remote 에서 받아온 데이타를 기본적으로는 콘솔에 출력한다. -o 옵션 뒤에 FILE 을 적어주면 해당 FILE 로 저장한다. (download 시 유용) | |
| -O | --remote-name | file 저장시 remote 의 file 이름으로 저장한다. -o 옵션보다 편리하다. | |
| -s | --silent | 정숙 모드. 진행 내역이나 메시지등을 출력하지 않는다. -o 옵션으로 remote data 도 /dev/null 로 보내면 결과물도 출력되지 않는다 | HTTP response code 만 가져오거나 할 경우 유리 |
| -v | --verbose | 동작하면서 자세한 옵션을 출력한다. | |
