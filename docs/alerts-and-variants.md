# Alerts and Variants

---

## Alerts

An alert is a canvas animation that plays when a specific event fires. Each overlay can have multiple alerts.

### Creating an alert

On the overlay page, click **+ New Alert** in the alerts panel. Type a name and press Enter. The alert editor opens.

From the top bar, set:

- **Event type** - the event that triggers this alert (e.g. `Twitch.Follow`, `Twitch.Sub`). An alert can respond to multiple event types.
- **Duration** - how long the alert plays in milliseconds.
- **Queue behavior** - whether this alert joins the queue or plays immediately.

Then build the alert using the canvas and layers. See [Visual Editor](visual-editor.md) for details.

### Enabling and disabling alerts

Each alert has a toggle on the overlay page. Disabled alerts will not play even when the event fires.

### Chance

Each alert has a chance percentage (0 to 100). When multiple alerts are bound to the same event type, Beacon picks one to play based on these weights. Set all alerts to 100 for equal odds. Leave a chance at 0 to disable weighted selection for that alert.

Variants also have their own chance percentage, used when multiple variants match the same event.

### Renaming and deleting

Click the pencil icon to rename an alert inline. Press Enter to confirm or Escape to cancel. You can also right-click an alert row for a context menu with rename, add variant, and delete options.

To delete, click the trash icon and confirm. The alert is removed from view immediately, but you have a few seconds to undo the deletion using the Undo button in the notification.

---

## Variants

Variants let you play a different version of an alert based on conditions. For example, you can show a different animation for T3 subs vs T1 subs, or play a special alert for raids over 100 viewers.

Each variant has its own canvas layout, its own duration, and its own condition rules. The parent alert acts as the default that plays when no variant condition matches.

### Creating a variant

Right-click an alert row and select **+ New Variant**. Give the variant a name. It will open in the editor where you can build its canvas and set its condition.

You can also duplicate an existing variant using the right-click menu on a variant row. Duplicating copies the canvas layout and condition, then opens the copy in the editor.

### Variant conditions

Click **Variant Setup** in the top bar of the variant editor to open the condition builder.

The condition builder has two modes:

- **Simple view** - add one condition at a time, all joined with AND. Use this for most cases, like `tier >= 3000` or `months >= 6`.
- **Advanced view** - build condition groups with AND and OR logic, and nest groups inside each other for complex rules.

A condition rule has three parts: a field name, an operator, and a value.

Supported operators: `==`, `!=`, `>`, `>=`, `<`, `<=`

Field names come from the event payload. You can check the Activity Feed to see what fields are available for a given event type. The condition builder also shows a list of known fields from live events and lets you click them to insert.

If a variant has no conditions set, it will match every event of the parent type and always play.

### Match mode

When an alert has variants, you can choose how Beacon picks which one to play if more than one condition matches.

- **Priority** - plays the first matching variant based on the order they are listed. Drag variants to reorder them.
- **Random** - picks randomly from all matching variants.

The match mode dropdown appears below the alert name when the alert is expanded.

### Variant order

Drag and drop variants to reorder them. Order matters in priority mode since the first match wins.

---

## Text-to-speech

Each alert and variant can have TTS configured independently. Open the TTS panel in the top bar of the editor.

Options:

- Enable or disable TTS for this alert.
- Voice selection.
- Text template using `{variable}` placeholders from the event data (e.g. `{user} just followed!`).
- Volume (0 to 100).
- Delay in seconds before TTS plays.
- Option to announce the action name before the message.

TTS uses the provider configured in **Settings > Audio**. See [Settings](settings.md) for setup.
