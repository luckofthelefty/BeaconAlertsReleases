# Activity Feed

The activity feed shows every event that comes in from Streamer.bot in real time. You can use it to monitor what is happening on your stream and check event data for building alert conditions.

---

## Connecting

The feed connects to Streamer.bot over a local WebSocket at `ws://127.0.0.1:8080` by default. If your Streamer.bot WebSocket server is on a different port, you can change the URL in the connection settings panel.

The connection status indicator at the top shows whether the feed is currently connected. To change the URL, click the gear icon at the top right of the page and enter the new address, then click **Reconnect**.

---

## The event list

Each row in the feed shows:

- The service the event came from (Twitch, YouTube, etc.)
- The event type as a colored badge (Follow, Sub, Raid, etc.)
- The viewer's display name
- A summary of the event details (tier, months, amount, message, etc.)
- The time the event arrived

Click the chevron on the right of any row to expand it and see the full event data. All fields from the Streamer.bot payload are shown as key/value pairs. Nested objects are flattened with dot notation, for example `user.name`.

---

## Tabs

The tab bar at the top groups events by service (Twitch, YouTube, etc.). Click a tab to filter the feed to that service.

To add or remove service tabs, click the **+** button at the right end of the tab bar and check or uncheck the services you want.

---

## Filtering event types

Some event types are hidden by default because they are noisy and not usually useful (chat messages, viewer count updates, connection lifecycle events, etc.).

Right-click any service tab to open a menu with a **Filter events** option. This opens a searchable list of event types for that service where you can toggle each one on or off. From here you can also select all, deselect all, or reset to defaults.

---

## Customizing event display

Each event type can be customized to show different information or use different colors. Click **Customize** on any expanded event row to enter edit mode.

From there you can set:

- **Label** - override the badge text for this event type
- **User template** - a `{{fieldKey}}` template for the name column
- **Meta template** - a `{{fieldKey}}` template for the summary column, or toggle individual fields on or off
- **Badge color and background**
- **User text color and size**
- **Meta text color and size**

Insert buttons next to each template input let you add field tokens at the cursor position.

Click **Reset** to remove all customizations for that event type.

Customizations are saved to your browser's local storage and persist between sessions.

---

## Alert queue controls

Below the event feed there is an **Alert Queues** panel. This lets you monitor and control your alert queues without leaving the activity feed.

Global controls (apply to all queues at once):

- **Pause / Resume** - stops new alerts from playing across all queues. Events that arrive while paused stay in the queue.
- **Skip** - cuts the currently playing alert short on every queue.
- **Clear** - drops all queued alerts on every queue.
- **Mute TTS / Unmute TTS** - silences or restores text-to-speech across all queues.

Expand the panel with the arrow to see per-queue controls. Each row shows the queue name, blocking/non-blocking status, which overlays are assigned (and whether they are loaded in OBS), the currently playing alert, and how many are waiting. The same pause, skip, clear, and mute controls are available per queue.

---

## Event storage

The feed keeps the last 1000 events in local storage. They persist between app restarts.
