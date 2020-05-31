
# IT Will Online Judge - Back end

- 기본적으로 IT Will Online Judge - Back end는 Qingdao University의 Online Judge Server 모듈의 Docker Version을 사용합니다.
- 현재 기존의 레거시 코드 한글 패치를 적용한 상황입니다.

## 환경 세팅

### Linux

1. 의존성 설치

    ```bash
    sudo apt update && sudo apt install python3-pip
    ```

2. Docker 설치

    `sudo curl -sSL get.docker.com | sh`
    
    참고： [https://docs.docker.com/install/](https://docs.docker.com/install/)

3. Docker-compose 설치

    `sudo pip3 install docker-compose`

### Windows

Windows에서는 체험용으로만 제공되므로, 실제 서버를 구축하려는 목적으로는 사용하지 마세요.  
만약 꼭 필요하다면, 가상 머신을 사용하여 Linux를 설치하고 Linux에 Online Judge를 설치하시기 바랍니다.

아래 내용은 Windows 10 x64의 `Powershell`에서 적용됩니다.

1. Windows용 Docker를 설치
2. Docker Settings 설정 클릭
3. `Shared Drives` 메뉴에서 Online Judge를 설치하려는 디스크(예를 들면, D드라이브)에 체크하고 `Apply` 클릭
4. Windows의 계정 암호를 입력하여 파일 공유
5. `Python`, `pip`, `git`, `docker-compose` 등을 설치 (설치 방법은 검색하면 많이 있습니다.)

## 설치

1. Docker image 복사

    ```bash
    git clone -b 2.0 https://github.com/IllIIIllll/OnlineJudgeDeploy.git && cd OnlineJudgeDeploy
    ```

2. 서비스 시작

    ```bash
    sudo docker-compose up -d
    ```

인터넷 속도에 따라 약 5분 ~ 30분 정도면 서버 구축이 완료되며, 서버 구축에 관한 모든 과정은 관리자가 관여할 필요가 없습니다.

`docker-compose` 수행이 완료되면, `sudo docker ps -a`를 실행하여 STATUS를 확인합니다. STATUS가 `Up xxx (healthy)`라면 정상 작동 상태이고, `unhealthy` 또는 `Exited (x) xxx`이면 로그아웃 상태입니다.

## 접속

웹 브라우저를 통해 서버의 HTTP 80 포트 혹은 HTTPS 443 포트로 접속할 수 있습니다.

백그라운드 관리 경로는 `/admin`이며, 최상위 관리자 계정은 `root` / `rootroot`로 설정되어 있습니다.

**`root` 계정의 암호는 반드시 수정하시기 바랍니다.**

기타 Online Judge에 관련된 상세 내용은 [이곳](http://docs.onlinejudge.me/)을 참고하기기 바랍니다.

## 커스텀

2.0 버전에서는 몇몇의 자주 쓰이는 설정을 관리자 계정으로 로그인하여 백그라운드 관리에서 설정할 수 있습니다.

즉, 직접 코드를 변경할 필요는 없습니다.

만약 수정 또는 2차 개발이 필요하다면 각 모듈의 **README**를 참고하세요.

수정 또는 2차 개발이 완료되면 자체 Docker 미러를 구축하고, `docker-compose.yml`을 수정하세요.

## 문제가 발생할 경우

[이곳](http://docs.onlinejudge.me/#/onlinejudge/faq)을 참고하거나, [issue](https://github.com/QingdaoU/OnlineJudgeDeploy/issues)페이지에 작성바랍니다.


## 오픈소스 라이센스
[MIT](http://opensource.org/licenses/MIT)
