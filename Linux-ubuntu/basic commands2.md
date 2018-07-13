# 패키지 형식

패키지이름_버전-개정번호\_아키텍쳐.deb 로 명명되며 우분투가 데비안 리눅스에서 파생되었기 때문에 확장명은 *.deb이다. 초창기에 리눅스에 새로운 프로그램을 설치하는 것이 어려워서 설치한 후에 바로 실행할 수 있는 설치 파일을 만들게 되었는데 이게 패키지다.

# dpkg

apt-get 이전의 패키지를 설치하는 명령어인데 의존성 문제 때문에 apt-get을 쓰게 되었다.

```bash
dpkg -l 패키지 // 해당 패키지가 있는지 확인한다.
dpkg --info 패키지 // 해당 패키지의 정보를 보여준다.
dpkg -i 패키지 // 패키지를 설치한다.
dpkg -r 패키지 // 패키지를 제거한다.
```

mysql 5.7을 설치할 때 의존성 문제로 에러가 발생했다. mysql 5.7을 설치하기 위해선 다른 패키지를 설치해야 하는데 어떤 deb 파일을 설치해야 할지 알기가 어렵다. 이렇기 때문에 apt-get 명령어를 사용하는 것이다.

# apt-get

의존성이 있는 다른 패키지를 자동으로 설치해준다. /etc/apt/sources.list 파일에 저장되어 있는 우분투 패키지 저장소에 가서 해당 패키지와 의존성이 있는 패키지를 가져와 자동으로 설치해주는 아주 괜찮은 명령어이다.

```bash
apt-get -y install 패키지이름 // -y를 붙이면 물어보지 않고 바로 설치한다는 것
apt-get update // /etc/apt/sources.list 파일 내용 수정되면 다운받을 패키지 목록 업데이트
apt-get remove 패키지이름 // 제거
apt-get autoremove // 사용하지 않는 패키지 제거
apt-get clean // 내려받기한 파일 및 과거의 파일 제거
```

# apt-cache

의존성 문제를 확인하는 명령어이다.

```bash
apt-cache show 패키지이름 // 패키지 정보 출력
apt-cache depends 패키지이름 // 의존성 정보 출력
apt-cache rdepends 패키지이름 // 해당 패키지에 의존하고 있는 패키지 목록 출력
```

# 패키지의 4가지 종류

패키지를 다운받는 사이트로 4가지 종류가 있다.

* main : 공식으로 지원하는 무료 소프트웨어
* universe : 지원하지 않는 무료 소프트웨어
* restricted : 공식으로 지원하는 유료 소프트웨어
* multiverse : 지원하지 않는 유료 소프트웨어