# Docker

### LXC

* LinuX Containers
* docker는 리눅스 컨테이너부터 시작한 기술임
* 단일 컴퓨팅 시스템에 설치된 리눅스 운영체제 상에서, 다른 영역과 완전히 분리된 별도의 리눅스 시스템을 운영할 수 있는 리눅스 커널 기술
* docker는 리눅스 커널에 LXC 기술을 사용해 리눅스 컨테이너를 만들고 리눅스 컨테이너 상에서 별도로 구성된 파일 시스템에 시스템 설정 및 응용 프로그램을 실행할 수 있도록 하는 기술
* 초기 docker는 LXC기술을 기반으로 구현되었으나 최근에는 별도의 컨테이너 기술을 구현해 사용하고 있음



### docker Engine

* docker는 서버/클라이언트 구조로 이루어짐
* 서버는 docker daemon process 형태로 동작함
  * 데몬이란, 보통 계속 실행 중인 프로그램으로 이해하면 됨
* docker daemon process에 요청하기 위해 프로세스간 통신 시법이 필요하며 docker에서는 Rest API를 사용함
* docker command는 일종의 클라이언트
  * docker command를 내리면 결국 내부적으로 Rest API를 사용해 docker daemon process를 호출하는 방식



### docker image

* docker 컨테이너를 생성하기 위한 명령들의 가진 탬플릿
* 여러 이미지를 layer로 쌓아서 원하는 형태의 이미지를 만들 수 있음
  * 예) ubuntu 이미지에, nginx 웹서버 이미지를 쌓아서 웹서버 이미지를 만듦



### docker container

* docker image가 리눅스 컨테이너 형태로 실행한 상태
* docker daemon에서 LXC로 리눅스 컨테이너를 생성 > docker image에 포함된 명령을 실행해 docker container를 만들고 실행함