# 이동주 | Dongju Lee

## Backend Lead Engineer | AI/LLM Systems | Event-Driven Architecture | Security Intelligence

안녕하세요! 저는 대규모 데이터 처리, 실시간 스트리밍 시스템, AI 에이전트 설계 경험을 갖춘 백엔드 리드 엔지니어입니다.  
기술적 의사결정과 시스템 아키텍처에 깊은 이해를 가지고 있으며, 비즈니스 가치 창출을 최우선으로 생각합니다.

### 🔗 Links

- [GitHub](https://github.com/dongju93)
- [GitHub Gist](https://gist.github.com/dongju93)
- [Blog](https://dongju93.github.io/blog/)
- [Portfolio](https://www.notion.so/dongjulee/Portfolio-e0c6d62ecfba4c3996a920c69322afd3?source=copy_link)

### 💼 Professional Experience

- **Software Engineer**, Pinolike (2024.05 - 현재)
- **Project Manager**,ClumL (2023.06 - 2024.04)
- **Consultant**, DailySoft (2021.01 - 2023.06)

### 🛠 Technical Skills

**Programming Languages**: Python, Go, TypeScript

**Backend & Frameworks**: FastAPI, Prefect, CrewAI, LangChain

**Data & Infrastructure**:

- Database: PostgreSQL, MariaDB, MongoDB, SQLite, TimescaleDB
- Streaming: Apache Kafka, Debezium (CDC), Apache Flink
- Search & Analytics: Elasticsearch, Grafana
- Caching & Messaging: Redis

**DevOps & Tools**: Docker, Kubernetes, Nginx, GitHub Actions

**Architecture & Patterns**: Event-Driven Architecture, Repository Pattern, Microservices, AsyncIO

### 🎓 Education

- Bachelor of Science, Information & Communications Engineering  
  Induk University (2012 - 2019)

---

## 📌 Featured Projects

### [🍸 Cocktail Maker](https://github.com/dongju93/cocktail-maker)

**칵테일 제조 정보 및 재료 관리 플랫폼**

주류에 관심을 가지면서 느낀 칵테일 정보의 체계적 부족을 해결하기 위한 풀스택 프로젝트입니다. 다양한 기술을 실제 서비스 수준으로 적용해보는 경험의 장이 되었습니다.

**Key Features**:

- SuperTokens 기반 분산 인증 시스템 (세션 + JWT 혼합)
- 다중 데이터베이스 전략 (MongoDB + SQLite)
- 구조화된 JSON 로깅 (structlog)
- 자동화된 코드 품질 관리 (Ruff, Pyright)

**Tech Stack**: Python, FastAPI, React, MongoDB, SQLite, PostgreSQL, Docker

**API Docs**: [Cocktail Maker Documentation](https://dongju93.github.io/cocktail-maker/)

---

### [📊 Real-time Data Streaming System](https://github.com/dongju93/real-time-data-stream)

**초당 수천 건의 주식 거래 데이터 실시간 처리 시스템**

대용량 시계열 데이터 처리, 이상 탐지, 과거 데이터 조회를 모두 지원하는 이벤트 기반 아키텍처입니다.

**Core Solutions**:

1. **성능 최적화** - PostgreSQL `COPY` 명령 활용으로 벌크 삽입 성능 **수십 배 향상**
2. **LLM Hallucination 차단** - Hallucination 문제 완전 해결 (실제 웹 검색 기반 정보 추출)
3. **동적 스트리밍** - WebSocket을 통한 실시간 Tick/Ticker 변경 지원
4. **비동기 아키텍처** - asyncio 기반 동시성 관리로 수천 개 동시 연결 처리

**Tech Stack**:

- Backend: FastAPI, asyncpg
- Data: PostgreSQL + TimescaleDB, Kafka, Debezium (CDC)
- Stream Processing: Apache Flink
- Communication: WebSocket, SSE

**Architecture**:

```
PostgreSQL/TimescaleDB → Debezium (CDC) → Kafka → Flink
                             ↓
                        FastAPI App ← WebSocket/SSE ← Client
```

---

### [🤖 AI Agents Suite](https://github.com/dongju93/ai-agents)

**다중 AI 에이전트 협력 시스템**

#### 뉴스 큐레이션 에이전트

- YAML 기반 에이전트/작업 정의로 코드-설정 분리
- 뉴스 수집 → 다단계 요약 → 큐레이션 자동화
- Crew 기반 자율적 협업 오케스트레이션

#### 이직 도움 에이전트 ⭐ 핵심 프로젝트

**복잡한 멀티 에이전트 시스템 설계의 정점**

사용자 이력서를 기반으로 **최적의 채용 공고 발굴 → 이력서 최적화 → 기업 분석 → 맞춤형 면접 자료 생성**까지 자동화하는 종합 취업 지원 시스템입니다.

**Architecture**:

- 5개 전문 AI 에이전트 (Search, Matcher, Optimizer, Researcher, Interviewer)
- 6단계 비선형 워크플로우 (`context` 파라미터로 복잡한 데이터 흐름 관리)
- Pydantic 모델 기반 구조화된 데이터 처리

**핵심 문제 해결: LLM Hallucination 완전 차단**

- **문제**: Job Matching Expert가 허위 기업명/URL 생성
- **원인**: 과도한 프롬프트 복잡성 + 웹 검색 도구 미사용
- **해결**: 프롬프트 재설계 + 웹 검색 필수화 → **실제 데이터만 추출**

**Tech Stack**: CrewAI, LangChain, Firecrawl v2, Playwright, Pydantic

---

## 🚀 Key Achievements & Insights

### 성능 최적화

| Challenge                     | Solution                              | Result                              |
| ----------------------------- | ------------------------------------- | ----------------------------------- |
| 초당 수천 건 데이터 삽입 병목 | PostgreSQL `COPY` + `asyncpg`         | **수십 배 향상**                    |
| 동적 스트리밍 조건 변경       | asyncio 태스크 분리 (stream + listen) | 연결 유지 상태에서 실시간 변경 가능 |
| 타입 안전성 부족              | TOML 기반 설정 + 정적 타입 체크       | 런타임 에러 사전 방지               |

### 아키텍처 설계

- **이벤트 기반**: CDC + Kafka + Flink로 느슨한 결합, 높은 확장성 달성
- **비동기**: FastAPI + asyncio + asyncpg 전체 스택 비동기화로 동시성 극대화
- **다중 DB 전략**: 정형/비정형 데이터 특성에 맞춘 MongoDB + SQLite 활용
- **도구 기반 AI**: LLM의 한계를 외부 도구(웹 검색, 스크래핑)로 확장

---

## 📝 Latest Blog Posts

최신 기술 및 소프트웨어 엔지니어링에 대한 글을 [블로그](https://dongju93.github.io/blog/)에 공유합니다:

- [A High-Level Overview of PostgreSQL's Architecture](https://dongju93.github.io/blog/post.html?id=postgresql-architecture-overview)
- [Hidden Gems of Python API Frameworks: An In-Depth Analysis of Granian, Falcon and Tornado](https://dongju93.github.io/blog/post.html?id=python-api-frameworks-hidden-gems)
- [Python 3.15 Preview and CPython Evolution: PEP 799, PEP 782, and the Era of Free-threading](https://dongju93.github.io/blog/post.html?id=python-3-15-pep-preview)

---

## 🎯 What I Focus On

✨ **Scalability & Performance** - 대규모 데이터 처리와 시스템 성능 최적화

🏗️ **System Architecture** - 확장 가능하고 유지보수 용이한 설계

🤖 **AI/LLM Integration** - 실무 수준의 AI 시스템 구축 및 최적화

🔄 **Event-Driven Systems** - 느슨하게 결합된 마이크로서비스 아키텍처

🛡️ **Enterprise Solutions** - 보안, 안정성, 감시 기능을 갖춘 프로덕션 시스템

---

## 📊 GitHub Stats

![Dongju's GitHub Stats](https://github-readme-stats.vercel.app/api?username=dongju93&show_icons=true&theme=dark)

---

**항상 배움에 열려있고, 함께 좋은 소프트웨어를 만드는 것을 좋아합니다.**  
궁금한 점이 있으시면 연락주세요! 🙌
