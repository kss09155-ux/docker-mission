## 터미널 기본 조작

'''bash
pwd
/Users/username/docker-git-workstation-mission

ls -la
total ...
drwxr-xr-x ...
.git
Dockerfile
index.html

mkdir terminal-lab
cd terminal-lab
touch empty.txt
ls -la
total ...
empty.txt

cp empty.txt copied.txt
mv copied.txt renamed.txt
cat empty.txt

rm renamed.txt
cd ..
'''

---

## B. 파일 권한 실습

요구사항:
- 파일 1개
- 디렉토리 1개
- 권한 확인/변경
- 변경 전/후 비교

### 실습 예시
```bash
touch permission-file.txt
mkdir permission-dir

ls -ld permission-file.txt permission-dir

chmod 644 permission-file.txt
chmod 755 permission-dir

ls -ld permission-file.txt permission-dir

- 파일 권한 `644`는 소유자만 쓰기 가능하고, 나머지는 읽기만 가능하다.
- 디렉토리 권한 `755`는 소유자는 읽기/쓰기/실행이 가능하고, 나머지는 읽기/실행만 가능하다.

C. Docker 설치 및 점검
요구사항:

Docker 버전 확인
Docker 데몬 동작 확인
실행 명령
bash
📋 복사
docker --version
docker info
추가 운영 명령도 기록
bash
📋 복사
docker images
docker ps
docker ps -a
docker logs my-web-container
docker stats --no-stream my-web-container
docker stats는 종료하려고 오래 볼 필요 없이
--no-stream 옵션을 쓰면 한 번만 출력돼서 과제용으로 좋아요.

D. hello-world 실습
요구사항에 명시되어 있으니 꼭 넣어야 합니다.

bash
📋 복사
docker run --rm hello-world
README에 적을 핵심
Docker가 이미지를 가져왔는지
컨테이너가 정상 실행되었는지
“Hello from Docker!” 메시지가 출력되었는지

0. 지금까지 한 일 정리
지금 너는 이미 큰 산을 넘었어요.

완료된 것:

Git 설치 확인
OrbStack/Docker 환경 준비
작업 폴더 생성
Git 저장소 초기화
커밋 진행
index.html 생성
Dockerfile 작성
Docker 이미지 빌드 성공
컨테이너 실행 성공
http://localhost:8080 접속 성공
즉, 커스텀 Docker 이미지 + 포트 매핑 웹서버 실행은 성공입니다.
이건 과제 핵심 요구사항 중 매우 중요한 부분이에요. 잘했어요.

1. 이제부터의 목표
이제 남은 목표는 딱 3개예요.

목표 A. GitHub 저장소로 제출 가능하게 만들기
GitHub 저장소 생성
로컬 프로젝트 업로드
공개 저장소 또는 과제 규칙에 맞는 권한 설정
목표 B. 필수 실습 증거 보완하기
요구사항을 보면 단순히 웹 띄우는 것만으로는 부족해요.
다음도 증거가 있어야 해요:

터미널 기본 조작
파일 권한 실습
Docker 기본 명령
hello-world
ubuntu 컨테이너 실습
바인드 마운트
Docker 볼륨 영속성
Git 설정
GitHub/VSCode 연동
목표 C. README.md 하나로 전체 과제를 설명하기
README를 읽는 사람이:

“무슨 과제였는지”
“어떤 환경에서 했는지”
“어떤 명령을 쳤고 어떤 결과가 나왔는지”
“어디서 문제가 있었고 어떻게 해결했는지”
를 한 번에 이해할 수 있어야 해요.
2. 가장 먼저 할 일: “제출용 구조” 만들기
먼저 프로젝트 폴더 구조를 정리합시다.
지금 작업 디렉토리에서 아래처럼 구성하면 가장 깔끔해요.

예시:

bash
📋 복사
your-project/
├── README.md
├── Dockerfile
├── index.html
└── docs/
    └── images/
왜 이렇게 하냐?
README.md : 전체 설명
Dockerfile, index.html : 실제 소스
docs/images/ : 스크린샷 보관
3. 과제는 “명령 + 결과”가 중요하다
여기서 아주 중요한 포인트가 있어요.

과제 요구사항은 단순히 “했다”가 아니라
“무슨 명령을 쳤고, 어떤 결과가 나왔는지 기록하라” 예요.

즉 앞으로는:

명령어 실행
출력 결과 확인
중요한 것은 README에 코드블록으로 기록
필요한 것은 스크린샷 저장
이 방식으로 가야 합니다.

4. 전체 진행 순서
지금부터는 아래 순서로 가는 게 가장 안전합니다.

1단계. GitHub 저장소 생성
2단계. 현재 프로젝트 업로드
3단계. 필수 실습 빠진 것 수행
4단계. 스크린샷 정리
5단계. README 작성
6단계. 최종 push
7단계. GitHub에서 링크만으로 검증되는지 점검
5. 1단계: GitHub 저장소 생성
해야 할 일
GitHub에서 새 저장소를 만드세요.

저장소 이름 예시
text
📋 복사
docker-git-workstation-mission
권장 설정
Public
README 자동 생성은 안 해도 됨
.gitignore 없어도 됨
License 없어도 됨
6. 2단계: 로컬 프로젝트를 GitHub에 연결
GitHub 저장소를 만들었으면, 로컬 터미널에서 아래를 실행합니다.

bash
📋 복사
git remote add origin https://github.com/사용자이름/저장소이름.git
git branch -M main
git push -u origin main
확인
bash
📋 복사
git remote -v
정상 예시:

bash
📋 복사
origin  https://github.com/username/docker-git-workstation-mission.git (fetch)
origin  https://github.com/username/docker-git-workstation-mission.git (push)
7. 3단계: 필수 실습 항목 점검
이제 과제 요구사항을 하나씩 체크해야 합니다.
중요한 건 지금 다시 실행해도 괜찮다는 거예요.

과제용 증거가 부족하면 다시 실행해서 기록하면 됩니다.

8. 필수 항목별로 해야 할 것
A. 터미널 기본 조작 기록
요구사항:

현재 위치 확인
목록 확인(숨김 파일 포함)
이동
생성
복사
이동/이름변경
삭제
파일 내용 확인
빈 파일 생성
실습용 예시
작업 폴더 안에서 terminal-lab 같은 폴더 만들어서 해도 됩니다.

bash
📋 복사
pwd
ls -la
mkdir terminal-lab
cd terminal-lab
pwd
touch empty.txt
ls -la
cp empty.txt copied.txt
mv copied.txt renamed.txt
cat empty.txt
rm renamed.txt
cd ..
ls -la
README에 어떻게 적나?
md
📋 복사
## 터미널 기본 조작

```bash
pwd
/Users/username/docker-git-workstation-mission

ls -la
total ...
drwxr-xr-x ...
.git
Dockerfile
index.html

mkdir terminal-lab
cd terminal-lab
touch empty.txt
ls -la
total ...
empty.txt

cp empty.txt copied.txt
mv copied.txt renamed.txt
cat empty.txt

rm renamed.txt
cd ..
code
📋 복사

---

## B. 파일 권한 실습

요구사항:
- 파일 1개
- 디렉토리 1개
- 권한 확인/변경
- 변경 전/후 비교

### 실습 예시
```bash
touch permission-file.txt
mkdir permission-dir

ls -ld permission-file.txt permission-dir

chmod 644 permission-file.txt
chmod 755 permission-dir

ls -ld permission-file.txt permission-dir
설명도 README에 넣어야 함
644 = 소유자 rw-, 그룹 r--, 기타 r--
755 = 소유자 rwx, 그룹 r-x, 기타 r-x
README 예시 문장
md
📋 복사
- 파일 권한 `644`는 소유자만 쓰기 가능하고, 나머지는 읽기만 가능하다.
- 디렉토리 권한 `755`는 소유자는 읽기/쓰기/실행이 가능하고, 나머지는 읽기/실행만 가능하다.
C. Docker 설치 및 점검
요구사항:

Docker 버전 확인
Docker 데몬 동작 확인
실행 명령
bash
📋 복사
docker --version
docker info
추가 운영 명령도 기록
bash
📋 복사
docker images
docker ps
docker ps -a
docker logs my-web-container
docker stats --no-stream my-web-container
docker stats는 종료하려고 오래 볼 필요 없이
--no-stream 옵션을 쓰면 한 번만 출력돼서 과제용으로 좋아요.

D. hello-world 실습
요구사항에 명시되어 있으니 꼭 넣어야 합니다.

bash
📋 복사
docker run --rm hello-world
README에 적을 핵심
Docker가 이미지를 가져왔는지
컨테이너가 정상 실행되었는지
“Hello from Docker!” 메시지가 출력되었는지
E. Ubuntu 컨테이너 실습
요구사항:

ubuntu 컨테이너 실행
내부 진입
ls, echo 같은 간단 명령 수행
attach/exec 차이 간단 정리
추천 방식
초보자에게는 exec 방식이 가장 안전합니다.

bash
📋 복사
docker run -dit --name ubuntu-lab ubuntu bash
docker exec -it ubuntu-lab bash
컨테이너 내부에서:

bash
📋 복사
ls
echo "hello ubuntu"
exit
그 다음 상태 확인:

bash
📋 복사
docker ps -a
attach/exec 차이 정리 문장 예시
README에 이렇게 쓰면 좋아요:

md
📋 복사
- `docker attach`는 컨테이너의 메인 프로세스에 직접 연결한다.
- `docker exec -it <container> bash`는 실행 중인 컨테이너 안에 새로운 셸을 띄운다.
- 실습에서는 `exec`가 더 안전하고 자주 사용된다는 점을 확인했다.
F. 현재 만든 커스텀 Docker 이미지 정리
이건 이미 완료했으니 문서화만 잘 하면 됩니다.

너의 현재 Dockerfile
Dockerfile
📋 복사
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
이걸 README에서 어떻게 설명하나?
1) 어떤 베이스를 썼는지
기존 베이스 이미지: nginx:alpine
2) 왜 이걸 썼는지
정적 HTML을 쉽게 서비스하기 위해
3) 어떤 커스텀을 했는지
기본 NGINX 페이지 대신 index.html로 교체
4) 빌드 명령
bash
📋 복사
docker build -t my-web .
5) 실행 명령
bash
📋 복사
docker run -d --name my-web-container -p 8080:80 my-web
6) 확인 명령
bash
📋 복사
docker ps
docker logs my-web-container
G. 포트 매핑 증거
이것도 요구사항 핵심입니다.

실행 명령
bash
📋 복사
docker run -d --name my-web-container -p 8080:80 my-web
README에 설명해야 할 것
호스트 포트: 8080
컨테이너 포트: 80
브라우저 주소: http://localhost:8080
반드시 첨부할 것
주소창이 보이는 브라우저 스크린샷
가능하면 화면에 HTML 결과도 같이 보이게
예시 파일명:

text
📋 복사
docs/images/port-mapping-browser.png
README에 삽입:

md
📋 복사
![포트 매핑 접속 확인](docs/images/port-mapping-browser.png)
H. 바인드 마운트 실습
이건 아직 안 했을 가능성이 높아요.
반드시 해야 합니다.

바인드 마운트 목적
호스트 파일을 컨테이너에 직접 연결해서
호스트에서 파일을 수정하면 컨테이너에도 바로 반영되는 것을 보여주는 것.

실행 전 준비
현재 디렉토리에 index.html이 있다고 가정합니다.

기존 컨테이너와 구분해서 새로 실행
bash
📋 복사
docker rm -f my-web-bind
docker run -d --name my-web-bind -p 8081:80 -v "$(pwd)/index.html:/usr/share/nginx/html/index.html" nginx:alpine
브라우저 접속
text
📋 복사
http://localhost:8081
호스트 파일 수정
bash
📋 복사
echo '<h1>Bind Mount Updated</h1>' > index.html
cat index.html
브라우저 새로고침 후 변경 확인

README에 넣어야 할 증거
실행 명령