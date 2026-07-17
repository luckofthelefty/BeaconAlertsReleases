# Stream Tools

Beyond overlays and chat, LuckyBot manages the rest of the stream from dedicated pages in the sidebar.

---

## Home

The landing page: edit your stream title and category, see recent activity, jump to your overlays, and follow the getting-started walkthrough.

---

## Stats

Live counts for followers, subs, bits, tips, raids, and raiders, across tabs:

- **Session** - counts for the current stream. Resets automatically when you go live, or manually with Reset Session.
- **Totals** - all-time totals.
- **Aggregates** - weekly, monthly, and rolling 30-day counts, plus top cheerer and top tipper leaderboards.
- **Labels** - the latest and recent contributor per type (latest follower, latest sub, and so on).
- **Goals** - a target and progress bar per metric, with a Reset Goals action.

Click any count to edit it, for example to seed a starting number that matches another tracker. Everything here is available to widgets as live variables. See [Widgets](widgets.md).

---

## Polls & Predictions

Create and run Twitch polls and predictions without leaving the app.

- **Polls** - title plus two or more choices, a live results card while running, End Poll, and a poll history.
- **Predictions** - title plus outcomes, then Lock, **Pay out** the winning outcome, or **Cancel & refund**, with a prediction history.

Live poll and prediction bars also appear on the Activity and Chat pages while one is running.

---

## Channel Points

Manage channel point rewards in two tabs:

- **Editable** - rewards created through LuckyBot: create, edit, pause, and delete them.
- **Read-only** - rewards created elsewhere (the Twitch dashboard). These can be copied to LuckyBot to make an editable duplicate.

A **Redemption queue** lists pending redemptions with Approve all and Reject all controls.

---

## Moderation

- **Unban Requests** - review, approve, or deny pending unban requests.
- **Blocked Terms** - manage the channel's blocked term list.

Day-to-day moderation (timeouts, bans, chat modes, Shield mode) lives on the [Chat](chat.md) page.

---

## Video Manager

Browse your VODs and clips.

- **VODs** - browse past broadcasts and create clips from them with a draggable clip editor.
- **Clips** - browse, search, and sort clips, with multi-select, open, copy link, and download.

---

## OBS

Connect OBS under **Settings > Connections > OBS Studio** (enable the WebSocket server in OBS first). The OBS page then gives you:

- **Go Live / Stop Stream** and **Record / Stop Rec** buttons with a status pill.
- A **scene switcher** with the live scene tagged.
- A **Sources** panel to toggle source visibility in the current scene.
- An **Audio Mixer** with per-input mute and volume.

---

## Closed Captions

Live on-screen captions from a fully offline speech-to-text engine. No cloud service, nothing leaves your machine.

1. Add the **Closed Captions** overlay (Advanced tab of the New Overlay browser) to OBS and style it: font, colors, outline, position, line count, hold time, and a profanity filter.
2. On the Captions page, pick your microphone and click **Start captions**. The first start downloads the speech model (about 40 MB).
3. A live preview shows what viewers see. An option starts captions automatically when LuckyBot opens.

Recognition runs entirely offline, so accuracy varies with audio quality.
