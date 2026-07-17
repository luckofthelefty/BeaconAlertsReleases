# Chat

The Chat page is a full Twitch chat client: read and send chat, run moderation, and manage other channels you moderate, all inside LuckyBot. It works natively from your Twitch login.

---

## The chat view

Messages show badges, emotes (including BetterTTV, FrankerFaceZ, and 7TV), animated cheermotes, replies, and pronouns. First-time chatters and first messages of the stream can be highlighted, @-mentions of you can be colored, and non-English messages can show an English translation underneath.

Power-Up message effects and gigantified emotes render like native Twitch. Deleted and banned messages are struck through or removed, based on your setting.

Hover a message for quick actions: copy, reply, pin, shoutout, and moderation actions. Click a username for the viewer card.

During a shared chat session, a banner at the top shows the participating channels, and messages from other channels are tagged and shown with the source streamer's picture.

---

## Toolbar

Above the chat: **Marker** (drop a stream marker), **Clip** (create a clip), **Raid** and **Cancel raid**, **Shoutout**, the next ad countdown with a **Snooze ad** button, and **Chat settings**.

A collapsible **Mod** strip toggles Slow, Followers-only, Subs-only, Emote-only, and Unique-chat modes, plus Shield mode.

While a raid is outgoing, a bar shows the target, the live count of viewers ready, and a countdown, with a Cancel button. Live bars for hype trains, polls, predictions, and ads appear the same way.

---

## Sending

Type in the compose bar and press Enter. An emote picker, @-mention autocomplete, and :emote: autocomplete are built in. **Announce** sends the message as a Twitch announcement.

Slash commands are supported: `/ban`, `/unban`, `/timeout`, `/untimeout`, `/purge`, `/shoutout` (`/so`), `/clear`, `/raid`, `/unraid`, `/marker`, `/announce` (with color variants), `/slow`, `/followers`, `/subscribers`, `/emoteonly`, `/uniquechat` (each with an off variant), `/me`, and `/help`.

Messages can be sent from your account, or from a bot account via the Sending tab in chat settings.

---

## Moderating other channels

The tab bar holds your own channel plus any channels you moderate. Click the **+** tab to pick from channels where you are a moderator.

Each moderated tab is a full chat view with mod actions, pinned messages, channel point redemptions, polls, hype train and ad timers, and event cards (subs, gifts, raids) for that channel. Shared chat is attributed there too. Tabs drag to reorder, and each has a popout button and a remove button.

---

## Popouts and OBS

- Any chat tab can pop out to its own window.
- **Chat settings > Popouts** has an **OBS chat dock URL** you can add in OBS as a Custom Browser Dock, so chat lives inside OBS.
- The same tab builds an **OBS chat overlay** for showing chat on stream: transparent or dark background, message order, fade-out timing, text size, pinned message visibility, and an option to anonymize follower names. Copy its URL into a browser source.

---

## Chat settings

The settings modal has five tabs:

- **Display** - emote extensions, text size, badges, pronouns, timestamps, translation, first-time and mention highlights, trusted links.
- **Events** - which event cards appear in chat per channel (Subs / Gifts, Bits / Cheers, Raids, Follows, Announcements, Super Chats, Channel Points, Other) and their colors, plus an option to expand gift-sub recipients into individual lines.
- **Moderation** - whether deleted messages are struck through or removed entirely.
- **Sending** - send as your account or a bot account.
- **Popouts** - popout windows, the OBS dock URL, the OBS chat overlay builder, startup auto-open, and a chat connection reset.
