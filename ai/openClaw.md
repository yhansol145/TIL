# OpenClaw (오픈클로) macOS 설치 가이드

> ⚠️ **주의**: 별 수·출처 정보가 의심스러운 부분이 있습니다. 본인 판단으로 진행해주세요. 영상/추천 출처에 적힌 URL이 `https://github.com/openclaw/openclaw`와 정확히 일치하는지 먼저 확인하시는 걸 추천합니다.

---

## 단계별 설치 가이드

### 0단계 — 출처 한 번 더 확인 (선택)
브라우저로 https://github.com/openclaw/openclaw 직접 열어서 README 보고 npm 패키지명도 거기 적힌 그대로인지 확인. (이 가이드와 다르면 README 우선)

### 1단계 — 현재 환경 확인
터미널에서:
```bash
node --version
npm --version
brew --version
```
시작 상태 예시: Node v18.12.1 / npm 8.19.2 / Homebrew 4.1.12 → Node 버전이 낮아서 업그레이드 필요.

### 2단계 — Node.js 24로 업그레이드 (nvm 사용)
이미 nvm이 깔려있다면:
```bash
nvm install 24
nvm use 24
nvm alias default 24
node --version   # v24.x.x 나오면 OK
```
> ⚠️ `nvm alias default 24`는 새 터미널의 기본 Node 버전을 24로 바꿉니다. 다른 프로젝트가 Node 18 의존이면 그 프로젝트에선 `nvm use 18.12.1` 해야 함.

### 3단계 — openclaw 글로벌 설치
```bash
npm install -g openclaw@latest
```
설치 끝나면:
```bash
openclaw --version
```
버전 출력되면 성공. `command not found`면 PATH 문제 — `npm config get prefix` 확인 후 `$prefix/bin`을 `~/.zshrc`에 PATH 추가.

### 4단계 — 온보딩 마법사 실행
```bash
openclaw onboard --install-daemon
```
대화형 마법사가 묻는 것들:
- **모델 제공자**: Anthropic (Claude) / OpenAI / 기타
- **API 키**: 미리 발급 받아놓기
  - Anthropic: https://console.anthropic.com → API Keys
  - OpenAI: https://platform.openai.com → API keys
- **데몬 설치 여부**: Yes (백그라운드 자동 실행)
- **워크스페이스 경로** 등

### 5단계 — 정상 동작 확인
```bash
openclaw doctor
```
모든 체크 ✓ 나오는지 확인. 빨간 줄 있으면 그 메시지를 확인해서 해결.

데몬 등록 확인:
```bash
launchctl list | grep openclaw
```

### 6단계 — 첫 대화
```bash
openclaw agent --message "안녕, 잘 깔렸니?" --thinking high
```
응답 오면 끝.

---

## 문제 생기면

| 증상 | 해결 |
|---|---|
| `openclaw: command not found` | `npm config get prefix` 후 `$prefix/bin`을 PATH에 추가 |
| Node 버전 에러 | `nvm use 24` 다시 실행 |
| 데몬 권한 에러 | 시스템 설정 → 개인정보 보호 및 보안 → 백그라운드 항목 |
| API 키 인증 실패 | `openclaw onboard` 재실행해서 키 다시 입력 |

---

## 설정 파일 위치

- `~/.openclaw/openclaw.json` — 모델 / 인증 설정
- `~/Library/LaunchAgents/` — launchd plist (데몬 설치 시 생성)

## 참고 링크

- 메인 리포: https://github.com/openclaw/openclaw
- 문서: https://github.com/openclaw/docs
