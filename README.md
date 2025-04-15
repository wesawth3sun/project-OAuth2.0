# 🚀 OAuth 기반 간편 결제 REST API 프로젝트

![Spring Boot](https://img.shields.io/badge/SpringBoot-3.4.4-brightgreen?style=for-the-badge&logo=Spring%20Boot&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-orange?style=for-the-badge&logo=MySQL&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=Docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=Prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=Grafana&logoColor=white)
> 소셜 로그인 연동과 안전한 결제 처리를 위한 Rest API 기반 사이드 프로젝트

## 📋 프로젝트 개요
- **OAuth 2.0 표준 인증** 기반 멀티 플랫폼 로그인 시스템
- 실시간 결제 처리와 거래 내역 관리 기능
- 마이크로서비스 아키텍처 기반 확장성 보장

## ✨ 주요 기능
### 🔐 인증/인가 시스템
- `Google/GitHub/Kakao/Naver/Apple` 소셜 로그인 연동
- JWT 토큰 발급/갱신/검증 자동화
- 역할 기반 접근 제어(RBAC) 구현

### 💳 결제 처리 시스템
- 카카오페이/토스페이 연동 결제 게이트웨이
- 결제 상태 추적 시스템(준비→진행→완료)
- 부분 취소/전체 취소 기능 지원

### 📊 데이터 관리
- 사용자 프로필 정보 암호화 저장
- 거래 내역 영수증 시스템
- 일별/월별 결제 집계 리포트

## 🛠 기술 스택
| 분야       | 기술 요소                     |
|------------|------------------------------|
| Backend    | Java 21, Spring Boot 3.4.3   |
| DB         | MySQL 8.0, Hibernate 6.2     |
| Security   | Spring Security 6.1, JWT     |
| Infra      | Docker 24.0                  |
| Monitoring | Prometheus, Grafana          |

## 🏗 시스템 아키텍처 - 도메인 주도 설계(DDD) 원칙을 적용
```text
src/
├── main
│ ├── java/com/payment
│ │ ├── config # 글로벌 설정
│ │ └── domain
│ │ ├── member # 사용자 도메인
│ │ │ ├── controller # 회원 관련 API
│ │ │ ├── service # 회원 비즈니스 로직
│ │ │ ├── repository # 회원 데이터 접근 계층
│ │ │ └── dto # 회원 DTO 클래스
│ │ │
│ │ └── payment # 결제 도메인
│ │ ├── controller # 결제 관련 API
│ │ ├── service # 결제 처리 로직
│ │ ├── repository # 결제 데이터 접근 계층
│ │ └── dto # 결제 DTO/Request/Response
│ │
│ └── resources
│   └── application.yml # 환경설정
``` 
## ✅ 엔드포인트 정리

| 엔드포인트          | 메소드 | 설명               |
|--------------------|--------|--------------------|
| /api/v1/payments   | POST   | 신규 결제 생성     |
| /api/v1/payments   | GET    | 결제 내역 조회     |
| /api/v1/payments/{id} | DELETE | 결제 취소       |


## ⚙️ 설치 및 실행

application.yml 파일 설정

```yaml
jwt:
  secret: ${JWT_SECRET}
  expiration: 3600000 # 1시간
```


## 📸 화면 예시
![결제 흐름 다이어그램](https://via.placeholder.com/800x400?text=Payment+Flow+Diagram)

📬 contect: suunn001@email.com

