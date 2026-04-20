# Alerts and Variants

---

## Alerts

An alert is a canvas animation that plays when a specific Streamer.bot event fires. Each overlay can have multiple alerts, and each alert is tied to one event type.

### Creating an alert

On the overlay page, click **+ New** in the alerts panel on the right. Type a name and press Enter. The alert editor opens.

From the top bar, set:

- **Event type** - the Streamer.bot event that triggers this alert (e.g. `Twitch.Follow`, `Twitch.Sub`)
- **Duration** - how long the alert plays in milliseconds
- **Queue behavior** - whether this alert goes into the queue or fires immediately

Then build the alert using the canvas and layers. See [Visual Editor](visual-editor.md) for details.

### Enabling and disabling alerts

Each alert has a toggle on the overlay page. Disabled alerts will not play even when the event fires. This is useful for seasonal or temporary alerts you want to keep configured but not active.

### Renaming and deleting

Click the pencil icon to rename an alert inline. Press Enter to confirm or Escape to cancel.

To delete, click the trash icon and then confirm with the checkmark. You can also right-click an alert row for a context menu with rename and delete options.

---

## Variants

Variants let you play a different version of an alert based on conditions. For example, you can show a different animation for T3 subs vs T1 subs, or play a special alert for raids over 100 viewers.

Each variant has its own canvas layout, its own duration, and its own condition rules. The parent alert acts as the default that plays when no variant condition matches.

### Creating a variant

Right-click an alert row and select **+ New Variant**, or expand the alert row with the arrow on the left and use the variant creation form at the bottom.

Give the variant a name. It will open in the editor where you can build its canvas and set its condition.

### Variant conditions

The condition builder is in the top bar of the variant editor. Conditions are rules built from event data fields.

A simple rule checks one field against a value, for example `tier == 3000`. You can combine multiple rules using AND or OR groups.

Supported operators: `==`, `!=`, `>`, `>=`, `<`, `<=`

Field names come from the Streamer.bot event payload. You can check the Activity Feed to see what fields are available for a given event type.

### Match mode

When an alert has variants, you can choose how Beacon picks which one to play if more than one condition matches.

- **Priority** - plays the first matching variant based on the order they are listed. Drag variants to reorder them.
- **Random** - picks randomly from all matching variants.

The match mode dropdown appears when you expand an alert row on the overlay page.

### Variant order

Drag and drop variants to reorder them. Order matters in priority mode since the first match wins.

---

## Text-to-speech

Each alert and variant can have TTS configured independently. Open the TTS panel in the top bar of the editor.

Options:
- Enable or disable TTS for this alert
- Voice selection
- Text template using `{variable}` placeholders from the event data (e.g. `{user} just followed!`)
- Volume (0 to 100)
- Delay in seconds before TTS plays
- Option to announce the action name before the message

TTS requires a StreamElements account. See [Settings](settings.md) to configure it.
