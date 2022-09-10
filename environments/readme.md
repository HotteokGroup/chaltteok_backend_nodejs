# 환경설정 구성

## .1 `/environments` 내 환경설정 파일 생성

```
.local.env 👉 로컬 환경
.dev.env 👉 개발 환경
```

원하는 환경에 맞춰 위 파일명에 맞춰 빈 파일을 생성합니다

## .2 아래 내용 작성

```
# ####################################
# DB Settings
# 데이터베이스 세팅 with Prisma
# ####################################
DATABASE_URL="mysql://root:root@localhost:3306/chaltteok?connect_timeout=100&pool_timeout=100&socket_timeout=100"
```

빈 파일에 위 내용을 작성합니다

## 환경설정 파일 validation process

// TODO
