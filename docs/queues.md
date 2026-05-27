# Queues

Queues control how alerts are played back. Without a queue, all alerts fire the moment their event comes in, which can cause them to stack or overlap. Queues let you manage the timing.

---

## Queue types

**Blocking** - alerts play one at a time. Each alert waits for the previous one to finish before it starts. Use this when you want alerts to play cleanly in sequence.

**Non-blocking** - alerts play immediately regardless of what else is playing. Use this for things like sound effects or overlays that do not need to be sequential.

---

## Creating a queue

Go to **Queues** in the sidebar and click **+ New Queue**. Give it a name. New queues start as blocking by default. You can toggle the type after creation.

---

## Assigning overlays to a queue

Queues are assigned per overlay. On the Overlays page, each overlay card has a queue dropdown. Pick the queue you want that overlay's alerts to use.

If an overlay has no queue assigned, its alerts play immediately without any queuing.

---

## Queue card controls

Each queue card in the Queues page shows the queue name, whether it is blocking or non-blocking, and a list of the overlays assigned to it.

From the card you can:

- **Toggle blocking/non-blocking** - click the badge on the card to switch the queue type.
- **Rename** - click the pencil icon.
- **Delete** - click the trash icon and confirm with the checkmark. Overlays that were using the deleted queue will fall back to no queue.

---

## Controlling playback

Pause, skip, clear, and mute controls for queues are in the **Activity Feed** page, not here. The Activity Feed has both global controls that apply to all queues at once and per-queue controls in the expandable queue panel at the bottom of the feed.

See [Activity Feed](activity-feed.md) for details.
