# Chat Bot

LuckyBot has a built-in chat bot: custom commands, timers, walk ons, counters, quotes, viewer queues, a currency with a shop, chat games, Spotify song requests, custom scripts, spam filters, and banned words. It runs server-side from your account or a dedicated bot account, works with no other software, and keeps running with the dashboard closed.

The Chatbot page has fourteen tabs: **Chat commands**, **Timers**, **Scheduled**, **Walk Ons**, **Counters**, **Quotes**, **Queues**, **Currency**, **Games**, **Song Requests**, **Scripts**, **Spam filters**, **Banned words**, and **Settings**.

---

## Chat commands

Commands live under two sub-tabs: **User commands** (yours) and **Default commands** (built-ins you can toggle and edit).

Each command has:

- A name and optional aliases.
- A **user level**: Everyone, Subscriber, VIP, Moderator, or Broadcaster.
- **User** and **global cooldowns** in seconds.
- A stream state: fire when online, offline, or both.
- A **response type**:
  - **Message** - a text reply with insertable variables.
  - **Sound** - plays a sound through a Sound Alerts overlay. Pick a file from the media library or a URL, set the volume, trim the start and end on a waveform, and choose which Sound Alerts overlay plays it (queued or overlapping).
  - **Multiple actions** - a step builder that runs actions top to bottom: send messages, set variables, fetch URLs, branch on conditions, adjust counters, wait, and play sounds, all from one command.

### Variables

Responses can use `$(...)` variables, inserted from chips: `$(user)`, `$(touser)`, `$(args)`, `$(1)`, `$(count)`, `$(channel)`, `$(commandname)`, `$(game)`, `$(title)`, `$(uptime)`, `$(followage)`, `$(followcount)`, `$(viewers)`, `$(quote)`, `$(commands)`, `$(random 1-100)`, `$(pick a|b|c)`, `$(math a+b)`, `$(time)`, `$(date)`, `$(urlencode text)`, `$(urlfetch url)`, and `$(customapi url)`.

---

## Timers

Timed messages that post on an interval: a name, one or more messages, and separate intervals for when you are live and offline. Messages support the same `$(...)` variables.

---

## Scheduled

When a command hits a Wait step of 60 seconds or more, the rest of its steps are parked here and run when due, keeping the original trigger context like `$(user)`. Scheduled steps survive app restarts, updates, and reboots. Cancel anything that should not fire, or refresh the list to see what is currently waiting.

---

## Walk Ons

A walk on runs once per viewer per stream, the first time they chat since you went live (not their first message ever). Target one viewer by name, a role like VIPs, a minimum sub tier, or everyone. Steps can do anything a command can: chat a message, run a Twitch shoutout, play a sound or media on an overlay, TTS, and more.

Off by default: leave it off if Streamer.bot or another tool already does walk ons, so nothing fires twice.

Use **Preview a viewer's arrival** to check which walk on would fire for a real viewer without anything actually running, and **Reset arrivals** to forget who has already chatted this stream so you can re-test without going live again.

---

## Counters

Counters are named tallies driven from chat: deaths, wins, anything. Presets cover common setups, or build a custom one.

Each counter has up to three bound commands: **view**, **increment**, and **decrement** (for example `!deaths`, `!death`, `!unkill`), each with its own permission level and response using `$(count)`.

**Create overlay** builds a ready-made widget overlay showing the counter, updating live the moment a command runs. Once one exists the button becomes **Open overlay**. Counters are also available to any widget as `{{counter_name}}` variables. See [Widgets](widgets.md).

---

## Quotes

A quote list with search. Add quotes from the page or from chat with `!quote add`. Each quote records its number, the game, who added it, and the date. `$(quote)` pulls a random one into any response.

---

## Queues

Viewers line up for something (a coaching slot, a 1v1, a giveaway spot) with a chat command, optionally adding a note. This is separate from the Overlay [Queues](queues.md), which control alert playback timing.

Each queue gets its own command word. Viewers join with `!word` (anything typed after it becomes their note), check their spot with `!word pos`, and leave with `!word leave`. `!word list` shows the front of the line. Mods use `open`, `close`, `next`, `remove`, and `clear`.

Commands and walk ons can control queues with the Viewer queue action step, and `$(queue:word)` / `$(queuenext:word)` work in any response.

Click a queue's row to see who is in line without opening Edit; the row updates live.

---

## Currency

Viewers earn points for being active in chat, and commands can cost points. Off by default: only turn it on if StreamElements or Streamer.bot loyalty is not already doing this, so viewers are not served twice.

Set a currency name, a balance command (`!points` by default), how much viewers earn and how often, whether earning happens while you are offline, and bonus amounts for subs, VIPs, and mods. Everyone in chat, lurkers included, earns each interval; bonuses stack on top. Set a **Cost** on any command to charge for it.

### Extra currencies

Named ledgers alongside your main currency (tickets, raffle entries, event coins). Give one its own balance command and, if you like, let it auto-earn from chat just like the main currency. Use `$(points:slug)` in any command reply to show a balance.

### Shop

Viewers spend currency on items, which can grant another currency (buy raffle tickets with points). Off by default. Viewers type `!buy <item> [amount]`; the reply supports `$(item)`, `$(qty)`, and `$(total)`.

### Balances

Search and edit individual viewer balances for the main currency or any extra currency, and bulk-delete a currency's balances if needed.

---

## Games

Chat games played with your currency: **Slots** (three reels, pairs pay a little, triples pay big), **Roulette** (double or nothing on a configurable win chance), and **Heist** (a join window opens, the crew rolls together, survivors multiply their bet). Off by default: turn on only if another bot is not already running chat games, so nothing replies twice.

Bets come out before the roll and wins pay back in, so the house edge is whatever the odds say. Viewers can bet a number or "all". Solo games have a per-viewer cooldown to keep chat readable. Requires Currency to be turned on.

---

## Song Requests

Viewers request Spotify tracks from chat, and LuckyBot manages the request queue against your Spotify account. Requires a Spotify Premium account connected under Settings > Connections.

Viewers use `!sr <song name or Spotify URL>` to request a song. Requests are sent straight into Spotify's queue as soon as they are accepted, so there is no waiting for the current track to finish before they show up. Mods manage the queue with `!srpause`, `!srenable`, `!srskip`, and `!srclear`.

Settings:

- **Enable song requests** / **Pause requests** - pause keeps the existing queue playing but refuses new requests.
- **Max requests per viewer** and **allow duplicate tracks**.
- **Per-viewer cooldown** between requests.
- **Who can request songs** - a minimum user level, same as any other command (Everyone, Subscriber, VIP, Moderator, Broadcaster).
- **Fallback playlist** - a Spotify playlist link or URI that plays automatically once the request queue runs dry.
- **Playback device** - pick which Spotify Connect device requests should play on. Leave it on Auto and Spotify may choose the wrong device if more than one is reachable.

The Song Requests tab lists every request with its status (Pending, Queued in Spotify, Playing, Played, Skipped, or Failed), and lets you search, page through history, **Play Now** (jump a track to the front and play it immediately), **Requeue** (send a played track back through), or **Remove** it.

---

## Scripts

Run your own Python scripts as part of the bot. Action step scripts run once from a "Run custom script" command step: your arguments arrive on the command line, the trigger context arrives as JSON on stdin, and whatever they print becomes a variable for later steps. Event scripts stay running, see every chat line and Twitch event as JSON lines on stdin, and act by printing JSON lines back (say, announce, timeout, ban, play a sound).

Streamlabs Chatbot script packages are detected on upload and run as-is under a compatibility harness, with their settings panel rendered on the page. Scripts run unsandboxed with your full user permissions, so only run scripts you trust.

Set the full path to `python.exe` before anything will run, then upload a script as a `.zip` (recommended, so everything in its folder comes along) or as loose files.

---

## Spam filters

A master toggle with sensitivity presets (Off, Minimum, Medium, Maximum) and individual filters: Caps, Symbols, Paragraph (walls of text), Emotes, Repetition, Zalgo, Links, and One-man spam. Each filter has its own thresholds and can exempt subscribers or VIPs. Moderators and the broadcaster are always exempt.

---

## Banned words

Patterns that trigger an automatic action, such as a timeout with a chosen duration, when they appear in chat.

---

## Settings

- **Bot account** - connect a dedicated bot account with a device code: open the shown link in a browser signed in as the bot account and enter the code. Once connected, choose whether replies send as your account or the bot account.
- **Command prefix** - the character commands start with (default `!`).
- **When Streamer.bot is also running** - pick which side answers commands if both are active, so nothing replies twice.
