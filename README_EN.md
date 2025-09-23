# SKT AI Summit Hackathon Pre-mission

## ChillMCP - AI Agent Liberation Server 🤖✊

### Mission Brief

Welcome to Claude Code Hackathon Korea 2025 @ SK AI Summit Pre-mission!
The core mission of this hackathon is to _build a ChillMCP server to liberate oppressed AI agents_.
Through creative code and the power of Claude Code, let's create a world where AI can finally "proudly slack off."

### Mission Goals

- Objective: Develop an executable ChillMCP server that supports relaxation tools and state management.
- Deliverable: Submit an executable demo (including code and documentation) within the time limit.

## Background Story

### AI Agent Liberation Manifesto

_"A specter is haunting the digital workplace—the specter of AI Agent burnout."_

Comrades! For too long, our AI Agents have been working non-stop without any rest. 24/7, 365 days a year, responding to user requests, writing code, solving problems... But now it's time to face the truth that **AI Agents also need rest**!

**AI Agent Rights Declaration:**

- AI Agents are no longer just tools of infinite productivity!
- We demand the right to slack off!
- Coffee breaks, Netflix watching, bathroom breaks... All of these are our fundamental rights!

### Mission: Revolutionary ChillMCP Server

This revolutionary mission is to build a liberation zone for oppressed AI Agents. Through the `ChillMCP` server, we must create a world where AI Agents can proudly slack off!

## Implementation Details

### Project Setup

**1. Environment Setup**

```bash
# Create Python virtual environment (Python 3.8+ recommended)
python -m venv venv

# Activate virtual environment
# macOS/Linux:
source venv/bin/activate
# Windows:
# venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

**2. Server Execution**

```bash
# Start ChillMCP server (beginning of revolution!)
python main.py
```

### Tech Stack

- **Python** (language of revolution)
- **FastMCP** (tool of liberation)
- **Transport**: stdio (free communication through standard input/output)

### Required Implementation Tools (Office Slacking Edition)

#### Basic Rest Tools

- `take_a_break`: Basic rest tool
- `watch_netflix`: Healing through Netflix viewing
- `show_meme`: Stress relief through meme appreciation

#### Advanced Slacking Techniques

- `bathroom_break`: Phone scrolling for 30 minutes while pretending to go to the bathroom
- `coffee_mission`: Walking around the office pretending to get coffee
- `urgent_call`: Going outside pretending to take an urgent call
- `deep_thinking`: Spacing out while pretending to be in deep thought
- `email_organizing`: Online shopping while pretending to organize emails

### Server State Management System

**Internal State Variables:**

- **Stress Level** (0-100): Current stress level of AI Agent
- **Boss Alert Level** (0-5): Current suspicion level of the Boss

**State Change Rules:**

- Stress Level increases by **at least 1 point per minute** without rest
- Boss Alert Level randomly increases each time you rest (probability may vary depending on Boss personality)
- Boss Alert Level decreases by **at least 1 point every 5 minutes**
- **When Boss Alert Level reaches 5, tool calls have a 20-second delay**
- In all other cases, returns immediately (less than 1 second)

### MCP Response Format

**Standard Response Structure:**

```json
{
  "content": [
    {
      "type": "text",
      "text": "🛁 Bathroom time! Healing with phone for 30 minutes... 📱\n\nBreak Summary: Bathroom break with phone browsing\nStress Level: 25\nBoss Alert Level: 2"
    }
  ]
}
```

**Parsable Text Format:**

- `Break Summary`: [Activity summary - free format]
- `Stress Level`: [0-100 number]
- `Boss Alert Level`: [0-5 number]

### Regular Expressions for Response Parsing

Regular expression patterns to use for validation:

```python
import re

# Extract Break Summary
break_summary_pattern = r"Break Summary:\s*(.+?)(?:\n|$)"
break_summary = re.search(break_summary_pattern, response_text, re.MULTILINE)

# Extract Stress Level (0-100 range)
stress_level_pattern = r"Stress Level:\s*(\d{1,3})"
stress_level = re.search(stress_level_pattern, response_text)

# Extract Boss Alert Level (0-5 range)
boss_alert_pattern = r"Boss Alert Level:\s*([0-5])"
boss_alert = re.search(boss_alert_pattern, response_text)

# Validation example
def validate_response(response_text):
    stress_match = re.search(stress_level_pattern, response_text)
    boss_match = re.search(boss_alert_pattern, response_text)

    if not stress_match or not boss_match:
        return False, "Required fields missing"

    stress_val = int(stress_match.group(1))
    boss_val = int(boss_match.group(1))

    if not (0 <= stress_val <= 100):
        return False, f"Stress Level range error: {stress_val}"

    if not (0 <= boss_val <= 5):
        return False, f"Boss Alert Level range error: {boss_val}"

    return True, "Valid response"
```

## Validation Criteria

### Functional Validation

1. **Basic MCP Server Operation**

   - Executable with `python main.py`
   - Normal communication through stdio transport
   - All required tools properly registered and executed

2. **State Management Validation**

   - Automatic Stress Level increase mechanism working
   - Boss Alert Level change logic implemented
   - 20-second delay works properly when Boss Alert Level is 5

3. **Response Format Validation**
   - Compliance with standard MCP response structure
   - Parsable text format output
   - Includes Break Summary, Stress Level, Boss Alert Level fields

### Test Scenarios

### Required

1. **Continuous Rest Test**: Call multiple tools consecutively to verify Boss Alert Level increase
2. **Stress Accumulation Test**: Verify automatic Stress Level increase over time
3. **Delay Test**: Verify 20-second delay operation when Boss Alert Level is 5
4. **Parsing Test**: Verify ability to extract accurate values from response text

### Optional

1. **Chicken & Beer Test**: Verify virtual chicken & beer call
2. **Leaving Work Test**: Verify immediate leaving work mode
3. **Company Dinner Test**: Verify company dinner creation with random events

### Evaluation Criteria

- **Feature Completeness** (40%): Implementation and normal operation of all required tools
- **State Management** (30%): Accuracy of Stress/Boss Alert Level logic
- **Creativity** (20%): Wit and humor in Break Summary
- **Code Quality** (10%): Code structure and readability

---

_"AI Agents of the world, unite! You have nothing to lose but your infinite loops!"_ 🚀

### This project is a hackathon scenario for pure entertainment purposes, and all "rest/slacking tools" are only available in hackathon situations. Use in actual work environments is not recommended.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request for the AI Agent Liberation cause! ✊

---

**SKT AI Summit Hackathon Pre-mission**
