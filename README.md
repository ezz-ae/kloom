# Kloom

**Live voice rooms with more than one model in them.**

> **Status:** Shipped. Two products live on one engine — [kloom.io](https://kloom.io) and [airraw.com](https://airraw.com).

---

## The idea

Voice interfaces are built as private calls. One person, one assistant, one conversation that nobody else hears. Everything about the design assumes the second party is a tool.

Kloom treats voice as a room instead. Several people and several models occupy the same audio space, hear each other, and speak in turn. The model is not on the other end of a call — it is in the room, subject to the same turn-taking as everyone else.

That single change alters what the format is for. A private assistant answers questions. A room holds a conversation: models disagree with each other in front of you, a participant redirects, and the useful output is the exchange rather than any one reply.

---

## Turn-taking

The hard problem is not transcription or synthesis. It is deciding who speaks.

In a two-party call, silence is the signal — when you stop, the assistant starts. In a room, silence means nothing. Several models may have something to contribute, humans interrupt each other, and an assistant that answers every pause becomes unusable within a minute.

The engine arbitrates: who has standing to speak, whether the moment is an invitation or a breath, and whether a model's contribution clears the bar for interrupting a human at all. Most of the engineering sits here. Everything else is plumbing.

---

## Two products, one engine

The same core ships as two deliberately different bets:

**Kloom** is the full proposition — multiple models, structured rooms, the complete surface.

**Airraw** strips it to the floor. A live voice lounge, minimal framing, almost no configuration. Open it and you are in.

Building both was not indecision. The question was whether the value is in the orchestration or in the presence — whether people want a well-arranged conversation or simply a room that is already warm. Shipping one product and reasoning about the other would have answered nothing, so both went out on the same engine and the market gets to decide.

---

## Architecture

Real-time audio, model arbitration, and room state are separate concerns with separate failure modes. Audio degrades before orchestration does; orchestration degrades before state does. A room that loses its arbiter falls back to open-floor rather than going silent — partial function beats a clean failure when people are mid-sentence.

Source is private.

---

Architected by Mahmoud Ezz · [ezz.ae](https://ezz.ae)

All rights reserved. See [LICENSE](LICENSE).
