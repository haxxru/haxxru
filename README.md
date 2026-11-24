<div align="center">

# I'm haxxru ☘️

### 만들고 끝내지 않고, 오래 잘 돌아가게 만듭니다.

트래픽 급증, 외부 서비스 장애, 동시 요청처럼 **실제 운영에서 터지는 문제**를<br>
설계 단계부터 고민하는 백엔드 개발자입니다.

<br>

| 3,507 | 1,250 | 90% | 127ms |
|:---:|:---:|:---:|:---:|
| 최대 동시 접속 | 실제 행사 회원 | SSE 트래픽 절감 | 3,000 VU 평균 응답 |

<a href="mailto:baxt_tt@naver.com"><img src="https://img.shields.io/badge/Email-03C75A?style=flat-square&logo=naver&logoColor=white"></a>
<a href="https://haxxru.vercel.app"><img src="https://img.shields.io/badge/TIL_Blog-haxxru.log-20C997?style=flat-square"></a>

</div>

<br>

## 🔒 Personal Projects

> 실제 사용자를 받아 운영한 서비스라 레포는 비공개입니다.

### 🎟 선착순 티켓팅 · QR 체크인 서비스

`1인 풀스택` `실제 행사 운영` · 회원 **1,250명** · 티켓 **499장** · 현장 체크인 **441건**

- 조건부 UPDATE · UNIQUE 제약 · Idempotency Key로 **정원 초과 · 중복 발급을 DB에서 차단**
- k6 3,000 VU 부하 테스트로 OOM을 찾아 Redis 캐시 · Bulkhead 적용, 평균 응답 **9.37s → 127ms**

<img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"> <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"> <img src="https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white"> <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square">

### 📊 실시간 댓글 순위 집계 · 발표 서비스

`1인 풀스택` `대형 방송 발표에 사용` · 최대 동시 접속 **3,507명** · 30일 방문자 **74,870명**

- SSE를 변경분만 보내는 델타 전송으로 바꿔 **트래픽 90% 절감**
- Supabase → Vercel KV → 로컬 스냅샷 **3단 폴백**으로 외부 장애에도 발표 유지

<img src="https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white"> <img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white"> <img src="https://img.shields.io/badge/SSE-FF6F00?style=flat-square"> <img src="https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white"> <img src="https://img.shields.io/badge/Cloudflare-F38020?style=flat-square&logo=cloudflare&logoColor=white">

<br>

## 👥 Team Projects

### 💍 Wedge — 예비부부와 웨딩 프리랜서를 잇는 역경매 매칭 플랫폼

`2026.06 · 2주` `4인 팀` `데브코스 AIBE6` `🏆 우수 팀 선정 (5팀 중)`

**담당** 회원 인증 · 구인/제안 · 커뮤니티 · CI/CD · AWS 배포

- 🔑 **인증 기반을 1주 차에 완성** — JWT · 이메일 인증 · Google/Kakao OAuth2를 하나의 JWT 흐름으로 통합해, 팀원 3명이 개발 기간 내내 인증 때문에 막힌 적이 없었습니다
- ♻️ **Refresh Token 회전** — Redis에 회원별 토큰을 두고 재발급마다 교체해 기존 토큰 재사용을 차단했습니다
- 🚀 **CI/CD 구축** — GitHub Actions에서 MySQL · Redis로 통합 테스트를 돌리고, Docker 이미지로 EC2에 배포했습니다. 멀티 스테이지 빌드로 이미지를 약 300MB 줄여 t2.micro에서도 안정적으로 운영했습니다
- 🔒 **HTTPS 배포 문제 해결** — Mixed Content를 Caddy 리버스 프록시와 Let's Encrypt 자동 발급으로 해결했습니다

<img src="https://img.shields.io/badge/Java_21-007396?style=flat-square&logo=openjdk&logoColor=white"> <img src="https://img.shields.io/badge/Spring_Boot_4-6DB33F?style=flat-square&logo=springboot&logoColor=white"> <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"> <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"> <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white">

[🔗 서비스](https://wedge-tawny.vercel.app) · [📦 Repository](https://github.com/prgrms-aibe-devcourse/AIBE6_Project2_Team05)

<br>

### 🃏 Pokade — 포켓몬 카드 실거래 시세 조회와 안전 거래 플랫폼

`2026.07 – 2026.08` `팀 프로젝트` `데브코스 AIBE6 파이널`

**담당** 매물 · 거래 도메인, 거래 상태 흐름, 결제 · 정산, 관리자 신고 · 검수 · 배송

- 🔄 **거래 상태 흐름 설계** — `ACTIVE → TRADING → 발송 → 검수 → 배송 → SOLD · 정산`까지 상태 전이를 규칙으로 관리했습니다
- 🛡 **중복 구매 방지** — `ACTIVE`인 매물만 `TRADING`으로 바꾸는 조건부 UPDATE로 동시 구매 시 선점을 하나만 허용하고, 선점에 실패하면 결제를 즉시 취소해 구매자 손해가 남지 않게 했습니다
- 💰 **정산 정합성** — 구매확정 시 결제 · 포인트 정산 · 매물 상태를 함께 처리해 데이터가 서로 다른 상태를 가리키지 않게 했습니다
- ⏰ **장기 미체결 매물 관리** — 30일 가격 조정 알림, 60일 자동 만료 배치를 만들되 거래 중인 매물은 건드리지 않게 했습니다

<img src="https://img.shields.io/badge/Java_21-007396?style=flat-square&logo=openjdk&logoColor=white"> <img src="https://img.shields.io/badge/Spring_Boot_4-6DB33F?style=flat-square&logo=springboot&logoColor=white"> <img src="https://img.shields.io/badge/JPA-59666C?style=flat-square&logo=hibernate&logoColor=white"> <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"> <img src="https://img.shields.io/badge/Toss_Payments-0064FF?style=flat-square"> <img src="https://img.shields.io/badge/JUnit_·_Mockito-25A162?style=flat-square">

[🔗 서비스](https://pokade.store) · [📦 Backend](https://github.com/prgrms-aibe-devcourse/AIBE6_FinalProject_Team05_BE) · [📦 Frontend](https://github.com/prgrms-aibe-devcourse/AIBE6_FinalProject_Team05_FE)

<br>

## 🛠 Tech Stack

### Backend

<img src="https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=openjdk&logoColor=white"> <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"> <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white"> <img src="https://img.shields.io/badge/JPA-59666C?style=for-the-badge&logo=hibernate&logoColor=white"> <img src="https://img.shields.io/badge/QueryDSL-0288D1?style=for-the-badge"> <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white">
<br>
<img src="https://img.shields.io/badge/Node.js-5FA04E?style=for-the-badge&logo=nodedotjs&logoColor=white"> <img src="https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white"> <img src="https://img.shields.io/badge/WebSocket-010101?style=for-the-badge"> <img src="https://img.shields.io/badge/Resilience4j-4A4A4A?style=for-the-badge">

### Frontend

<img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white"> <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black"> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white"> <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white"> <img src="https://img.shields.io/badge/React_Query-FF4154?style=for-the-badge&logo=reactquery&logoColor=white">

### Database

<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"> <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"> <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white"> <img src="https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white"> <img src="https://img.shields.io/badge/Flyway-CC0200?style=for-the-badge&logo=flyway&logoColor=white">

### Infra & DevOps

<img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge"> <img src="https://img.shields.io/badge/Amazon_RDS-527FFF?style=for-the-badge"> <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white"> <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"> <img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white"> <img src="https://img.shields.io/badge/PM2-2B037A?style=for-the-badge&logo=pm2&logoColor=white">
<br>
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white"> <img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white"> <img src="https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white"> <img src="https://img.shields.io/badge/k6-7D64FF?style=for-the-badge&logo=k6&logoColor=white">

### Tools

<img src="https://img.shields.io/badge/IntelliJ_IDEA-000000?style=for-the-badge&logo=intellijidea&logoColor=white"> <img src="https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge"> <img src="https://img.shields.io/badge/Cursor-000000?style=for-the-badge&logo=cursor&logoColor=white"> <img src="https://img.shields.io/badge/DBeaver-382923?style=for-the-badge&logo=dbeaver&logoColor=white"> <img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white"> <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white"> <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white">

<br>

## 📖 Currently Learning

<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white"> <img src="https://img.shields.io/badge/System_Design-FF9800?style=for-the-badge"> <img src="https://img.shields.io/badge/TDD-25A162?style=for-the-badge">

<br>

## 🌱 Contributions

<div align="center">

<img src="https://github-readme-activity-graph.vercel.app/graph?username=haxxru&theme=github-compact&hide_border=true" width="100%">

</div>
