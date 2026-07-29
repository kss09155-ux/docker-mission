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


docker run --rm hello-world
README에 적을 핵심
Docker가 이미지를 가져왔는지
컨테이너가 정상 실행되었는지
“Hello from Docker!” 메시지가 출력되었는지
