# Quartz 프로젝트 배포 가이드

## Docker Compose를 사용한 Self-Hosting 방법

### 필요 조건
- Docker
- Docker Compose

### 배포 단계

1. 프로젝트 클론
```bash
git clone <repository-url>
cd quartz
```

2. Docker Compose 실행
```bash
docker-compose up -d
```

3. 브라우저에서 접속
```
http://localhost
```

### 설정 변경

- `nginx.conf`: Nginx 서버 설정을 변경할 수 있습니다.
- `docker-compose.yml`: 포트 또는 기타 Docker 설정을 변경할 수 있습니다.

### 서버 이름 변경

프로덕션 환경에서 사용하려면 `nginx.conf` 파일의 `server_name` 값을 실제 도메인 이름으로 변경하세요.

```
server_name example.com;
```

### 빌드 후 배포

Quartz 프로젝트를 변경한 후 다시 빌드하려면:

```bash
docker-compose down
docker-compose up -d --build
``` 