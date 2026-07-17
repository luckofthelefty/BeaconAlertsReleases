# Chat Bot

LuckyBot has a built-in chat bot: custom commands, counters, timed messages, quotes, spam filters, and banned words. It runs server-side from your account or a dedicated bot account, works with no other software, and keeps running with the dashboard closed.

The Chatbot page has seven tabs: **Chat commands**, **Timers**, **Counters**, **Quotes**, **Spam filters**, **Banned words**, and **Settings**.

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

## Counters

Counters are named tallies driven from chat: deaths, wins, anything. Presets cover common setups, or build a custom one.

Each counter has up to three bound commands: **view**, **increment**, and **decrement** (for example `!deaths`, `!death`, `!unkill`), each with its own permission level and response using `$(count)`.

**Create overlay** builds a ready-made widget overlay showing the counter, updating live the moment a command runs. Once one exists the button becomes **Open overlay**. Counters are also available to any widget as `{{counter_name}}` variables. See [Widgets](widgets.md).

---

## Timers

Timed messages that post on an interval: a name, one or more messages, and separate intervals for when you are live and offline. Messages support the same `$(...)` variables.

---

## Quotes

A quote list with search. Add quotes from the page or from chat with `!quote add`. Each quote records its number, the game, who added it, and the date. `$(quote)` pulls a random one into any response.

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
