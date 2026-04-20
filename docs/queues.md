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

## Queue controls

Each queue card in the Queues page shows which overlays are using it. You can:

- **Pause** - stops new alerts from playing. Events that come in while paused will wait in the queue.
- **Skip** - skips the currently playing alert and moves to the next one.
- **Clear** - removes all waiting alerts from the queue.
- **Mute** - alerts still play but TTS is silenced.

---

## Renaming and deleting

Click the pencil icon on a queue card to rename it.

To delete a queue, click the trash icon and confirm with the checkmark. Overlays that were using the deleted queue will fall back to no queue.
