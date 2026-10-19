# Worked examples

Referenced from `SKILL.md`. Two full examples of the intended pacing.

## 1. Replacing a definition-first opening

Suppose the opening line is `__threadfence()` establishes device-scope ordering but is not a barrier. That is accurate, and it does not help a reader who does not yet have the picture. A better way in:

> A fence puts an order on one thread's memory operations: at the scope it names, that thread's earlier writes become visible before its later ones. It works inside a single thread's instruction stream. Bringing threads together is a different job, and that one belongs to a barrier. In CUDA, `__threadfence()` is a device-scope ordering primitive: it orders one thread's memory operations, and it says nothing about where any other thread has reached.

The rewrite leads with what a fence does, and mentions the barrier once, at the point where the confusion actually lives.

Treat all of this as a guide to pacing; change the vocabulary, the detail, and the examples to fit the actual question.

## 2. A term card, then a number that argues against itself

> **HOL blocking** — a first-in-first-out queue, so a large item at the head keeps a small urgent item behind it from leaving.
> **Why it is a problem here** — bulk data and tiny control messages share one queue, and a FIFO cannot tell which one is urgent.
> **What it is confused with** — congestion and packet loss. The network can be completely uncongested and this still happens, because the two flows share a queue.

Then, instead of listing the result, stop on it:

> Caching cut the number of embeddings sent over the network by 55%, yet lookup latency fell only 4.9%.

Don't doubt the measurement first; ask which path the optimisation touches. Latency is set by the slowest leg of each lookup. Removing 55% of the vectors leaves the other 45% still crossing the network and still waited on. The volume moved; the critical path barely did.

That pairing — card, then a number that resists the obvious reading — is the pattern to reproduce. The aim is a model that survives contact with the next surprising number.
