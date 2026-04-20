# Activity Feed

The activity feed shows every event that comes in from Streamer.bot in real time. You can use it to monitor what is happening on your stream, check event data for building alert conditions, and replay events to test alerts.

---

## Connecting

The feed connects to Streamer.bot over a local WebSocket at `ws://127.0.0.1:8080` by default. If your Streamer.bot WebSocket server is on a different port, you can change the URL in the connection settings panel.

The connection status indicator at the top shows whether the feed is currently connected.

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

The tab bar at the top groups events by service (Twitch, YouTube, etc.). Click a tab to filter the feed to that service. You can reorder tabs by dragging them.

To add or remove service tabs, open the connection settings panel and toggle services on or off.

---

## Filtering event types

Some event types are hidden by default because they are noisy and not usually useful (chat messages, viewer count updates, connection lifecycle events, etc.). You can control which types are shown using the event type filter in the connection settings panel.

Click the filter icon on any tab to search for a specific event type and toggle it on or off.

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

## Replaying events

You can replay any event in the feed to trigger alerts as if the event had just happened. This is useful for testing without going live.

---

## Event storage

The feed keeps the last 1000 events in local storage. They persist between app restarts.
