### Gauransh Sharma

I build LLM backends for production apps, and the mobile clients that sit on top of them. Python, TypeScript, Swift, Flutter. On weekends I build Mac apps and small things that run on my own machine.

### Things I've built

**[braid](https://github.com/gauransh18/braid)** · multi-agent coding harness · TypeScript, Tauri

Splits a goal into a task graph and gives each task to a coding agent (Claude Code, Codex, Gemini CLI or a NIM model) in its own git worktree. A task merges only if the tests pass, a reviewer agent approves, and the tests pass again on the merged tree. A merge that breaks the tree gets rolled back. Everything lands on an integration branch, and an interrupted run picks up where it stopped. CLI, live dashboard and a desktop app for macOS and Windows.

<img src="https://raw.githubusercontent.com/gauransh18/braid/main/docs/images/dashboard-running.png" width="720" alt="braid dashboard with a task graph mid-run">

**[meet-agent](https://github.com/gauransh18/meet-agent)** · an AI that joins your Google Meet · Playwright, WebRTC, Ollama, whisper.cpp, Kokoro

Send a Meet link to a Telegram bot and Tekki joins as a participant with a face and a voice. Meet has no bot API, so it pretends to be the devices: `getUserMedia` is swapped inside the page for a canvas (video) and a WebAudio node (audio). Chrome won't hand decoded WebRTC audio back to WebAudio, so to hear the call the container records its own PulseAudio sink. All models run locally.

<img src="https://raw.githubusercontent.com/gauransh18/meet-agent/master/docs/board.gif" width="720" alt="Tekki drawing a diagram on a shared whiteboard during a call">

**[Spacebar](https://github.com/gauransh18/spacebar)** · live thumbnails of every macOS Space · Swift

macOS has no public API for this, so most people assume it can't be done. It uses three private CoreGraphics Services calls to list and switch Spaces. Off-screen windows are captured with ScreenCaptureKit using `onScreenWindowsOnly: false` and a desktop-independent window filter. Miss either one and you only get the Space you're on.

**[Perch](https://github.com/gauransh18/perch)** · coding agents in the notch · Swift

Shows every running Claude Code session in the notch, with a live tool feed and cost. You can approve tool calls from a diff preview with `⌘Y` / `⌘N`, and one click jumps back to the exact iTerm2, tmux or WezTerm pane the agent is running in.

**[NotchPrompter](https://github.com/gauransh18/notchprompter)** · teleprompter under the camera · Swift

Follows your voice with on-device speech recognition. A fuzzy matcher scores the last few spoken words against a look-ahead window, so ad-libs and skipped paragraphs don't throw it off. The panel uses `sharingType = .none`, so it stays out of screen recordings.

**[Doodle Pond](https://github.com/gauransh18/doodle-pond)** · one shared pond for the whole internet · three.js, Cloudflare D1

Draw a fish, release it, and catch other people's. If you keep a fish, it disappears from the pond for everyone. [Play it](https://doodlepond.pages.dev).

More Mac apps at [apps.gauranshsharma.com](https://apps.gauranshsharma.com). Smaller things: [Sound Garden](https://github.com/gauransh18/sound-garden), [commitai](https://github.com/gauransh18/commitai), [personal-mcp](https://github.com/gauransh18/personal-mcp), [roast-my-github](https://github.com/gauransh18/roast-my-github), and a [pump organ](https://github.com/gauransh18/Macbook-Harmonium---using-Lid-Angle-Sensor) that uses the MacBook lid as bellows.

### At work

- Coaching agent on Bedrock (Claude) with tool calling and SSE streaming. Hybrid RAG on Pinecone (BM25 plus Titan embeddings) and Mem0 for memory across sessions. Shipped an MCP server so users can run the whole coaching app from inside Claude or ChatGPT.
- Moved product scoring into a persisted batch pipeline so 500k+ products rank through an indexed lookup. It used to take 0.5 to 2s per item on every request.
- LLM character DMs with structured outputs, ElevenLabs audiobook narration, and offline reading in Expo. The outbox replays queued actions exactly once on reconnect.

[gauranshsharma.com](https://gauranshsharma.com) · [LinkedIn](https://linkedin.com/in/gauransh18) · [X](https://x.com/gauransh18_) · gauransh@gauranshsharma.com
