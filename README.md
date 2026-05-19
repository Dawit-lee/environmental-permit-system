# 🌿 환경기초시설 인허가 관리 시스템

![Status](https://img.shields.io/badge/status-in%20progress-yellow)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-6DB33F?logo=springboot&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-blue)

> 사기업 엔지니어링 회사의 프로젝트별 환경기초시설 인허가 생애주기를 통합 관리하는 웹 애플리케이션

---

## 📌 프로젝트 개요

| 항목 | 내용 |
|------|------|
| 목적 | 프로젝트별 인허가 현황·기한·문서를 한 곳에서 통합 관리 |
| 대상 사용자 | 민간 엔지니어링 회사 담당자 |
| 개발 형태 | 개인 포트폴리오 프로젝트 |
| 개발 기간 | 2026.05 ~ 2026.08 (3개월) |

### 배경

환경기초시설의 인허가는 설치허가, 가동개시신고, 정기검사, 변경허가, 갱신허가 등 수십 종의 절차가 프로젝트 전반에 걸쳐 발생합니다. 현장에서는 이를 엑셀·종이문서로 관리하며 아래 문제가 반복됩니다.

- 허가 만료 및 검사 기한 누락
- 법령 개정 대응 지연
- 문서 분산 보관으로 인한 이력 추적 불가

---

## 🗂 핵심 데이터 구조

```
회사 → 프로젝트 → 인허가 항목 → 진행 현황
```

> 예시: A엔지니어링 → 부산 하수처리장 증설 공사 → [설치허가, 가동개시신고, 정기검사] → 각 항목별 상태·기한·담당자 관리

---

## ✅ 주요 기능

- **인허가 대장 관리** — 허가번호·취득일·유효기간·담당기관 등록 및 이력 추적
- **기한 알림** — 갱신·검사·신고 기한 D-90/60/30/7 자동 알림
- **문서 보관함** — 허가증·검사성적서·신고서 파일 첨부 및 버전 관리
- **일정 캘린더** — 프로젝트별 인허가 일정 캘린더 뷰 시각화
- **현황 대시보드** — 인허가 준수율, 기한 임박 현황 통계

---

## 🛠 기술 스택

| 구분 | 기술 |
|------|------|
| Frontend | React 18, TypeScript, Tailwind CSS |
| Backend | Spring Boot 3.x (Java 17) |
| Database | PostgreSQL 16 |
| 파일 저장 | AWS S3 |
| 인프라 | Docker → 추후 AWS 전환 예정 |
| 인증 | JWT (자체 인증) |

---

## 📁 폴더 구조

```
env-permit-management/
├── frontend/               # React + TypeScript
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── api/
│   │   └── types/
│   └── package.json
├── backend/                # Spring Boot
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── com/envpermit/
│   │       │       ├── controller/
│   │       │       ├── service/
│   │       │       ├── repository/
│   │       │       └── domain/
│   │       └── resources/
│   │           └── application.yml
│   └── build.gradle
├── docker-compose.yml
└── README.md
```

---

## 🚀 로컬 실행 방법

### 사전 준비
- Java 17+
- Node.js 20+
- Docker Desktop
- PostgreSQL 16 (또는 Docker로 실행)

### 백엔드 실행
```bash
cd backend
./gradlew bootRun
```

### 프론트엔드 실행
```bash
cd frontend
npm install
npm run dev
```

### Docker로 전체 실행
```bash
docker-compose up -d
```

---

## 🗓 개발 로드맵

| 기간 | 작업 내용 | 상태 |
|------|----------|------|
| 1개월차 | 화면 설계 + DB 구조 + 기본 CRUD | 🔄 진행 중 |
| 2개월차 | 기한 알림 로직 + 문서 첨부 + 대시보드 | ⏳ 예정 |
| 3개월차 | 캘린더 뷰 + UI 다듬기 + 배포 | ⏳ 예정 |

---

## 📸 화면 스크린샷

> 개발 진행 중 — 추후 업데이트 예정

---

## 📄 License

[MIT](./LICENSE)
