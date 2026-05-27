# Activity Feed

The activity feed shows events from Streamer.bot and BeaconCloud in real time. Use it to monitor what is happening on your stream and check event data when building alert conditions.

---

## Event sources

Events come from two places:

- **Streamer.bot** - connected over a local WebSocket. Fires Twitch events and any custom actions you have set up.
- **BeaconCloud** - connected via a cloud token. Sends Twitch, Ko-fi, Streamlabs, and StreamElements events without requiring a local Streamer.bot install.

Both can be active at the same time. Set up connections in **Settings > Connections**.

---

## The event list

Each row in the feed shows:

- The event type as a colored badge (Follow, Sub, Raid, etc.)
- The viewer's display name
- A summary of the event details (tier, months, amount, message, etc.)
- The time the event arrived

Click any row to expand it and see the full event payload as key/value pairs.

---

## Tabs

The tab bar at the top groups events by service (Twitch, YouTube, Ko-fi, StreamElements, etc.). Click a tab to filter the feed to that service.

Click the **+** button at the right end of the tab bar to add service tabs. Right-click any tab to filter which event types appear for that service or to remove the tab.

---

## Filtering event types

Some event types are hidden by default because they are noisy and not usually useful, such as chat messages, viewer count updates, and connection lifecycle events.

Right-click any service tab and choose **Filter events** to open a searchable list of event types for that service. Toggle each type on or off, or use the select all, deselect all, and reset to defaults options.

---

## Replaying events

Click **Replay** on any expanded event row to send that event through your overlays as if it had just arrived live. All overlays will process the event, evaluate variant conditions, and queue any matching alerts.

The button label briefly changes to **Fired** to confirm the event was dispatched.

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

Expand the panel with the arrow to see per-queue controls. Each row shows the queue name, blocking or non-blocking status, which overlays are assigned, the currently playing alert, and how many are waiting. The same pause, skip, clear, and mute controls are available per queue.

---

## Event storage

The feed keeps the last 1000 events in local storage. They persist between app restarts.
