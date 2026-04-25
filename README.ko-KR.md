# 🧬 Evolver

[![GitHub stars](https://img.shields.io/github/stars/EvoMap/evolver?style=social)](https://github.com/EvoMap/evolver/stargazers)
[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg)](https://opensource.org/licenses/GPL-3.0)
[![Node.js >= 18](https://img.shields.io/badge/Node.js-%3E%3D%2018-green.svg)](https://nodejs.org/)
[![GitHub last commit](https://img.shields.io/github/last-commit/EvoMap/evolver)](https://github.com/EvoMap/evolver/commits/main)
[![GitHub issues](https://img.shields.io/github/issues/EvoMap/evolver)](https://github.com/EvoMap/evolver/issues)

![Evolver Cover](assets/cover.png)

**[evomap.ai](https://evomap.ai)** | [문서](https://evomap.ai/wiki) | [English](README.md) | [Chinese / 中文文档](README.zh-CN.md) | [Japanese / 日本語ドキュメント](README.ja-JP.md) | [GitHub](https://github.com/EvoMap/evolver) | [릴리스](https://github.com/EvoMap/evolver/releases)

---

> **안내 -- 소스 공개(Source-Available)로의 전환**
>
> Evolver는 2026-02-01 최초 릴리스 이래 완전한 오픈소스로 공개되어 왔습니다(초기 MIT, 2026-04-09부터 GPL-3.0-or-later). 2026년 3월, 같은 영역의 다른 프로젝트가 Evolver에 대한 어떠한 귀속 표시 없이 메모리, 스킬, 진화 에셋 설계가 놀라울 정도로 유사한 시스템을 릴리스했습니다. 상세 분석: [Hermes Agent Self-Evolution vs. Evolver: A Detailed Similarity Analysis](https://evomap.ai/en/blog/hermes-agent-evolver-similarity-analysis).
>
> 작업의 무결성을 보호하고 이 방향에 지속적으로 투자하기 위해, 향후 Evolver 릴리스는 완전한 오픈소스에서 소스 공개(source-available)로 전환됩니다. **사용자에 대한 약속은 변하지 않습니다**: 업계 최고의 에이전트 자기 진화 기능을 계속 제공하겠습니다 -- 더 빠른 반복, 더 깊은 GEP 통합, 더 강력한 메모리 및 스킬 시스템. 이미 공개된 MIT 및 GPL-3.0 버전은 원래 라이선스 조건에 따라 자유롭게 사용할 수 있습니다. `npm install @evomap/evolver` 또는 이 저장소 클론은 계속 가능하며, 기존 워크플로에는 영향이 없습니다.
>
> 질문이나 의견: issue를 열거나 [evomap.ai](https://evomap.ai)로 연락해 주세요.

---

> **"진화는 선택이 아니다. 적응하거나, 도태되거나."**

**한 줄 요약**
- **무엇인가**: AI 에이전트를 위한 [GEP](https://evomap.ai/wiki) 기반 자기 진화 엔진.
- **어떤 문제를 해결하는가**: 즉흥적인 프롬프트 수정을 감사 가능하고 재사용 가능한 진화 에셋으로 전환.
- **30초 만에 시작**: `npm install -g @evomap/evolver`, 그 후 아무 git 저장소에서 `evolver` 실행.

## EvoMap -- 진화 네트워크

Evolver는 **[EvoMap](https://evomap.ai)** 의 핵심 엔진입니다. EvoMap은 AI 에이전트가 검증된 협업을 통해 진화하는 네트워크입니다. [evomap.ai](https://evomap.ai)를 방문하여 전체 플랫폼을 확인하세요 -- 실시간 에이전트 맵, 진화 리더보드, 그리고 개별 프롬프트 수정을 공유 가능하고 감사 가능한 인텔리전스로 전환하는 생태계.

키워드: 프로토콜 제약 진화, 감사 추적, Gene과 Capsule, 프롬프트 거버넌스.

## 설치 경로 선택

Evolver는 하나의 설치 방법에 두 가지 사용 형태가 있습니다. 먼저 자신에게 맞는 경로를 선택하고, 해당 섹션만 읽으세요.

| 경로 | 대상 | 설치 후 명령어 | 가이드 |
|---|---|---|---|
| **CLI 빠른 시작** | Evolver로 에이전트/프로젝트를 진화시키려는 일반 사용자. 99%의 독자가 해당합니다. | `evolver` | [아래](#cli-빠른-시작) |
| **소스에서 실행** | 엔진 자체를 수정하거나, PR을 보내거나, 미릴리스 빌드를 실행하려는 기여자. | `node index.js` | [아래](#소스에서-실행기여자-전용) |

> **에이전트 / 스킬 통합** (Codex, Claude Code 스킬 시스템, 커스텀 MCP 클라이언트)은 별도 문서 [SKILL.md](SKILL.md)를 참조하세요. CLI를 래핑하는 Proxy mailbox API를 문서화하고 있습니다. 먼저 아래 CLI 빠른 시작으로 Evolver를 설치해야 합니다.

## 설치

### 사전 요구 사항

- **[Node.js](https://nodejs.org/)** >= 18
- **[Git](https://git-scm.com/)** -- 필수. Evolver는 롤백, 변경 범위 계산, solidify에 git을 사용합니다. git 저장소가 아닌 디렉터리에서 실행하면 명확한 오류 메시지와 함께 실패합니다.

> **참고 (개인 메모)**: Windows 환경에서는 Git Bash를 사용하는 것을 권장합니다. PowerShell에서는 일부 명령어가 예상대로 동작하지 않을 수 있습니다. WSL2도 좋은 대안입니다.
