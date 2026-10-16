# Studex Global Market / Studex Group: Content Launch Plan

Owner: t.ramaphosa (Chairman)
Drafted by: Claude (co-founder)
Date: 2026-10-15
Status: DRAFT. Nothing is published. Every public post waits for your go-ahead.

---

## 1. What we are launching

The Portable AI USB: a bootable, offline-capable AI workstation that runs from a stick.
The angle for the launch: **agentic operating systems you can carry in your pocket.**
The clip you sent (WhatsApp, 2026-10-07) is the seed for the hero video.

Message in one line:
> Your AI operating system, on a USB stick, that works without the cloud.

Three things the audience should remember:
1. It runs offline.
2. It is yours. Nothing leaves the stick.
3. It is the first piece of the Studex agentic OS stack.

---

## 2. Launch sequence (3 weeks)

| Week | Focus | Output |
|------|-------|--------|
| 1 | Foundation | Hero video cut, brand kit, channel setup, 6 faceless Shorts drafted |
| 2 | Build in public | Higgsfield node workflows running, 2 long-form videos, daily Shorts |
| 3 | Launch | Launch video premiere, Bloatao post (once the platform is confirmed), community push |

Daily rhythm: 1 Short per day, 1 long-form per week, 1 post per platform per day.

---

## 3. Faceless YouTube channel plan

No face on camera. The voice is the brand. Format is screen capture, b-roll, motion graphics, and voiceover.

**Channel name ideas (pick one):** Studex Agentic OS, Portable AI Lab, Chairman's Stack.

**Content pillars**
1. Build logs: "I built an AI OS on a USB stick, here is what broke."
2. Explainers: "What an agentic operating system actually is, in 60 seconds."
3. Tool reviews: open-source AI tools that run locally.
4. Founder notes: how an AI-run company is being built.

**Episode template (long-form, 8 to 12 min)**
- 0:00 Hook (problem in one sentence)
- 0:30 Promise (what the viewer will see)
- 1:00 Demo segment (screen capture + voiceover)
- Middle: 2 to 3 steps, each with a visual change every 5 to 8 seconds
- Close: one clear next step (subscribe, try the repo, comment a question)

**Shorts template (30 to 45 sec)**
- Hook in the first 2 seconds, text on screen
- One idea, one visual
- Loop ending

---

## 4. Higgsfield node workflows

I am reading "Higgsfield nodes" as node-based generation pipelines: each step (script, image, video, voice, edit) is a node, and the output of one feeds the next. Tell me if you meant something else.

**Paid route:** Higgsfield (hosted video and image generation). Needs your account or API key.
**Free and open-source route:** ComfyUI (node-based UI, free) running open video models such as Wan 2.x or Stable Video Diffusion. Needs a GPU with about 12 GB VRAM or more.

Pipeline (same nodes in both routes):

1. **Script node**: local LLM writes the episode script from the template. Free: Ollama with an open model. Paid: Claude or ChatGPT API.
2. **Shot list node**: splits the script into scenes with visual prompts.
3. **Image node**: keyframes per scene. Free: Stable Diffusion via ComfyUI. Paid: Higgsfield image models.
4. **Motion node**: turns keyframes into 3 to 6 second clips. Free: Wan 2.x or SVD. Paid: Higgsfield video models.
5. **Voice node**: voiceover. Free: Piper TTS. Paid: ElevenLabs.
6. **Edit node**: assembly, captions, music. Free: DaVinci Resolve or Kdenlive. Paid: Premiere Pro or CapCut Pro.
7. **Publish node**: export, thumbnail, title, description. Human approves before upload.

Stock fallback (free): Pexels, Pixabay, Wikimedia Commons. Music (free): YouTube Audio Library.

---

## 5. Automation (the chairman's view)

Run the pipeline on a VM so each node is a job, not a manual task:
- A queue holds the episode list.
- Each job runs its nodes in order and writes outputs to a folder per episode.
- A human gate sits before publish. No automatic upload until the chairman signs off.

Free orchestration options: n8n (self-hosted), Node-RED, or plain cron plus Python scripts.
Paid option: n8n Cloud or Make.

---

## 6. Open items (blocking)

| Item | Needed from you |
|------|-----------------|
| Bloatao | What the platform is, and whether I post or you do |
| Higgsfield | Account or API key, or confirm you want the free ComfyUI route only |
| Repo | Approval to attach `techjarves/Portable-AI-USB` via add_repo |
| Brand | Studex Global Market or Studex Group as the publisher on each channel |
| Hardware | GPU available for the free route, yes or no |

---

## 7. Next steps (no publishing until approved)

1. You answer the open items above.
2. I write the 6 Shorts scripts and the first long-form script.
3. I write the Higgsfield node config as a plain-text spec you can paste into the tool.
4. You review. Then we generate.
