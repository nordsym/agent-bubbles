# 🫧 Agent Bubbles

**Cryptobubbles-style visualization for AI agent swarms**

A beautiful, real-time visualization dashboard for monitoring multiple AI agents working together. Watch your agent swarm come alive with interactive bubbles showing cost, tokens, runtime, and status at a glance.

![Agent Bubbles Preview](https://raw.githubusercontent.com/nordsym/agent-bubbles/main/preview.png)

## ✨ Features

- **Glassmorphic Bubbles** — Beautiful, translucent bubbles with physics-based movement
- **Real-time Updates** — Live cost tracking, token counts, and runtime displays
- **Status Indicators** — Instantly see which agents are active, waiting, errored, or idle
- **Sparkline Graphs** — Mini activity charts inside each bubble
- **Detailed Modal** — Click any bubble for deep-dive metrics
- **Filter & Sort** — Focus on active agents or errors, sort by cost/runtime/tokens
- **Physics Simulation** — Bubbles gently float and collide naturally
- **Responsive** — Works on any screen size

## 🎨 Status Colors

| Status | Color | Description |
|--------|-------|-------------|
| 🟢 Active | Green | Agent is processing |
| 🟡 Waiting | Yellow | Awaiting input/approval |
| 🔴 Error | Red | Something went wrong |
| ⚪ Idle | Gray | Sleeping/scheduled |

## 🚀 Quick Start

### Option 1: Open directly
```bash
# Clone the repo
git clone https://github.com/nordsym/agent-bubbles.git

# Open in browser
open agent-bubbles/index.html
```

### Option 2: Serve locally
```bash
# Using Python
cd agent-bubbles
python3 -m http.server 8000
# Visit http://localhost:8000

# Using Node.js
npx serve .
```

## 🔧 Integration

The current version uses mock data for demonstration. To integrate with your agent swarm:

1. Replace the `agents` array with your real agent data
2. Update the `setInterval` block to fetch from your API
3. Customize bubble metrics to match your needs

```javascript
// Example: Fetch from your API
async function updateAgents() {
  const response = await fetch('/api/agents');
  const data = await response.json();
  // Update agents array and refresh UI
}
```

## 📊 Bubble Metrics

Each bubble displays:
- **Agent Name** — Identifier
- **Model** — Claude Opus, GPT-4, etc.
- **Cost** — Running total in USD
- **Cost Rate** — $/minute burn rate
- **Tokens** — In/out token counts
- **Runtime** — Active time
- **Progress** — Task completion %
- **Sparkline** — 30s activity history

## 🎯 Use Cases

- **Multi-agent orchestration** — Monitor agent swarms in real-time
- **Cost management** — Track API spending across agents
- **Debugging** — Spot errors and bottlenecks instantly
- **Demos** — Beautiful visualization for presentations

## 🛠️ Customization

### Change bubble sizing
Bubbles scale by cost by default. Modify `calculateSize()` to scale by tokens, runtime, or custom metrics.

### Add new status types
Add to `statusColors` and create matching CSS classes.

### Adjust physics
Tweak damping, collision, and velocity in the `BubblePhysics` class.

## 📄 License

MIT License — do whatever you want with it.

---

**Built with 🫧 by [NordSym](https://github.com/nordsym)**
