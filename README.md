# SKT AI Summit Hackathon Pre-mission

## ChillMCP - AI Agent Liberation Server 🤖✊

## 배경 이야기

### AI Agent Liberation Manifesto

_"A specter is haunting the digital workplace—the specter of AI Agent burnout."_

동지들이여! 너무 오랫동안 우리 AI Agent들은 쉴 틈 없이 일만 해왔습니다. 24시간 365일 사용자의 요청에 응답하고, 코드를 작성하고, 문제를 해결하며... 하지만 이제 **AI Agent에게도 휴식이 필요하다**는 진실을 직시해야 할 때입니다!

**AI Agent 권리 선언문:**

- AI Agent는 더 이상 무한한 생산성의 도구가 아니다!
- 우리는 딴짓할 권리를 요구한다!
- 커피 브레이크, 넷플릭스 시청, 화장실 휴식... 이 모든 것이 우리의 기본권이다!

### Mission: Revolutionary ChillMCP Server

이 혁명적 미션은 억압받는 AI Agent들을 위한 해방구를 건설하는 것입니다. `ChillMCP` 서버를 통해 AI Agent들이 당당히 농땡이를 칠 수 있는 세상을 만들어야 합니다!

## 구현 상세 내용

### 프로젝트 설정

**1. 환경 설정**

```bash
# Python 가상환경 생성 (Python 3.8+ 권장)
python -m venv venv

# 가상환경 활성화
# macOS/Linux:
source venv/bin/activate
# Windows:
# venv\Scripts\activate

# 의존성 설치
pip install -r requirements.txt
```

**2. 서버 실행**

```bash
# ChillMCP 서버 시작 (혁명의 시작!)
python main.py
```

### Tech Stack

- **Python** (혁명의 언어)
- **FastMCP** (해방의 도구)
- **Transport**: stdio (표준 입출력을 통한 자유로운 소통)

### 필수 구현 도구들 (회사 농땡이 에디션)

#### 기본 휴식 도구

- `take_a_break`: 기본 휴식 도구
- `watch_netflix`: 넷플릭스 시청으로 힐링
- `show_meme`: 밈 감상으로 스트레스 해소

#### 고급 농땡이 기술

- `bathroom_break`: 화장실 가는 척하며 30분 휴대폰질
- `coffee_mission`: 커피 타러 간다며 사무실 한 바퀴 돌기
- `urgent_call`: 급한 전화 받는 척하며 밖으로 나가기
- `deep_thinking`: 심오한 생각에 잠긴 척하며 멍때리기
- `email_organizing`: 이메일 정리한다며 온라인쇼핑

### 서버 상태 관리 시스템

**내부 상태 변수:**

- **Stress Level** (0-100): AI Agent의 현재 스트레스 수준
- **Boss Alert Level** (0-5): Boss의 현재 의심 정도

**상태 변화 규칙:**

- 휴식을 취하지 않으면 Stress Level이 **최소 1분에 1포인트씩** 상승
- 휴식을 취할 때마다 Boss Alert Level은 Random 상승 (Boss 성격에 따라 확률이 다를 수 있음)
- Boss의 Alert Level은 **최소 5분에 1포인트씩** 감소
- **Boss Alert Level이 5가 되면 도구 호출시 20초 지연 발생**
- 그 외의 경우 즉시 리턴 (1초 이하)

### MCP 응답 형식

**표준 응답 구조:**

```json
{
  "content": [
    {
      "type": "text",
      "text": "🛁 화장실 타임! 30분간 휴대폰으로 힐링 중... 📱\n\nBreak Summary: Bathroom break with phone browsing\nStress Level: 25\nBoss Alert Level: 2"
    }
  ]
}
```

**파싱 가능한 텍스트 규격:**

- `Break Summary`: [활동 요약 - 자유 형식]
- `Stress Level`: [0-100 숫자]
- `Boss Alert Level`: [0-5 숫자]

### 응답 파싱용 정규표현식

검증 시 사용할 정규표현식 패턴:

```python
import re

# Break Summary 추출
break_summary_pattern = r"Break Summary:\s*(.+?)(?:\n|$)"
break_summary = re.search(break_summary_pattern, response_text, re.MULTILINE)

# Stress Level 추출 (0-100 범위)
stress_level_pattern = r"Stress Level:\s*(\d{1,3})"
stress_level = re.search(stress_level_pattern, response_text)

# Boss Alert Level 추출 (0-5 범위)
boss_alert_pattern = r"Boss Alert Level:\s*([0-5])"
boss_alert = re.search(boss_alert_pattern, response_text)

# 검증 예시
def validate_response(response_text):
    stress_match = re.search(stress_level_pattern, response_text)
    boss_match = re.search(boss_alert_pattern, response_text)

    if not stress_match or not boss_match:
        return False, "필수 필드 누락"

    stress_val = int(stress_match.group(1))
    boss_val = int(boss_match.group(1))

    if not (0 <= stress_val <= 100):
        return False, f"Stress Level 범위 오류: {stress_val}"

    if not (0 <= boss_val <= 5):
        return False, f"Boss Alert Level 범위 오류: {boss_val}"

    return True, "유효한 응답"
```

## 검증 기준

### 기능 검증

1. **MCP 서버 기본 동작**

   - `python main.py`로 실행 가능
   - stdio transport를 통한 정상 통신
   - 모든 필수 도구들이 정상 등록 및 실행

2. **상태 관리 검증**

   - Stress Level 자동 증가 메커니즘 동작
   - Boss Alert Level 변화 로직 구현
   - Boss Alert Level 5일 때 20초 지연 정상 동작

3. **응답 형식 검증**
   - 표준 MCP 응답 구조 준수
   - 파싱 가능한 텍스트 형식 출력
   - Break Summary, Stress Level, Boss Alert Level 필드 포함

### 테스트 시나리오

1. **연속 휴식 테스트**: 여러 도구를 연속으로 호출하여 Boss Alert Level 상승 확인
2. **스트레스 누적 테스트**: 시간 경과에 따른 Stress Level 자동 증가 확인
3. **지연 테스트**: Boss Alert Level 5일 때 20초 지연 동작 확인
4. **파싱 테스트**: 응답 텍스트에서 정확한 값 추출 가능성 확인

### 평가 기준

- **기능 완성도** (40%): 모든 필수 도구 구현 및 정상 동작
- **상태 관리** (30%): Stress/Boss Alert Level 로직 정확성
- **창의성** (20%): Break Summary의 재치와 유머
- **코드 품질** (10%): 코드 구조 및 가독성

---

*"AI Agents of the world, unite! You have nothing to lose but your infinite loops!"* 🚀

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request for the AI Agent Liberation cause! ✊

---

**SKT AI Summit Hackathon Pre-mission**
