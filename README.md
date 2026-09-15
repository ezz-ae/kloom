# Kloom

Every voice assistant ever shipped is built as a phone call. One person, one machine, a private line, nobody else listening. The whole design assumes the second party is a tool you are operating.

Kloom is built as a room instead. Several people and several models occupy one audio space, hear each other, and take turns. The model is not on the far end of a call — it is in the room, bound by the same rules about when to speak as everyone else.

That one change alters what the format is *for*. A private assistant answers questions. A room holds a conversation — models disagree with each other in front of you, somebody redirects, and the thing you walk away with is the exchange rather than any single reply. You stop asking and start listening, which is a different activity entirely.

Live at **[kloom.io](https://kloom.io)**.

---

## Turn-taking

The hard problem is not transcription and it is not synthesis. Both are solved and both are somebody else's business. The hard problem is deciding who speaks.

In a two-party call, silence is the signal: you stop, the assistant starts. In a room, silence means nothing at all. Several models may have something worth saying, humans talk over each other constantly, and a participant who answers every pause becomes intolerable inside of a minute — not wrong, just exhausting, which is worse.

So the engine arbitrates. Who currently has standing to speak. Whether this pause is an invitation or a breath. Whether what a model has to offer clears the bar for interrupting a human at all — because most of the time it does not, and knowing that is the product.

Almost all of the engineering lives here. The rest is plumbing.

---

## Airraw

The same engine ships as a second product that strips the idea to the floor. [airraw.com](https://airraw.com) is a live voice lounge: minimal framing, almost nothing to configure, open it and you are in.

Shipping both was not indecision. The open question was whether the value sits in the orchestration or in the presence — whether people want a well-arranged conversation, or simply a room that is already warm when they arrive. Those imply different products, and reasoning about it internally would have settled nothing. So both went out on one engine, and the market gets to answer.

---

## Failure

Real-time audio, model arbitration and room state are separate concerns with separate failure modes, and they fail in a deliberate order. Audio degrades before orchestration does. Orchestration degrades before state does.

A room that loses its arbiter falls back to an open floor rather than going quiet. This is the right call for the same reason it is the right call at a dinner table: when people are mid-sentence, partial function beats a clean failure. Silence is the one outcome a voice product cannot recover from.

---

## Status

Shipped. Two products live on one engine. Source is private.

---

Built by Mahmoud Ezz · [ezz.ae](https://ezz.ae)

All rights reserved. See [LICENSE](LICENSE).
