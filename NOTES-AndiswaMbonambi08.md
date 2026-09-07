## Assignment 2.1

### Question 1: Scrum or Kanban, for two different contexts

**Daily App (Shelf):** Kanban.
Shelf is solo, worked in short, irregular sessions, and the scope will shift as I actually
use the app and notice what's missing. Scrum asks me to commit to a fixed sprint scope and
run ceremonies (standup, sprint planning, retro) that only make sense with more than one
person to sync with — running them solo is just talking to myself on a schedule. Kanban's
continuous flow and pull-based WIP limits fit better: I add a card to "To Do" when an idea
occurs to me, pull it when I have a session free, and there's no sprint boundary I need to
hit or re-plan around when a session gets skipped.

**TrackFlow:** Scrum.
TrackFlow has multiple contributors who need to stay in sync, and Scrum's fixed cadence
(sprint boundaries, standups, reviews) gives the whole cohort shared checkpoints to
coordinate merges, demo progress, and re-negotiate scope together. That coordination
overhead is exactly what's missing — and unnecessary — when I'm the only person on the
project.

My answer differs between the two because the deciding factor isn't the type of project,
it's the number of people who need to stay coordinated.

### Question 2: A real trade-off

**Value:** Responding to change over following a plan.

**Decision:** How much detail to put into Shelf's initial epic list before I start building.

I could write a fully detailed backlog now, but since I'm still learning what a reading
tracker actually needs, a detailed upfront plan risks going stale before I even build half
of it. I'll lean toward responding to change: epics.md stays coarse so it can absorb what I
learn without a rewrite. Still, a completely planless backlog would leave me deciding
priorities from scratch every session, so I'll keep just enough structure to know the shape
of the whole project.

### Question 3: Critique and redesign

**Problems with the "TaskBoard Pro" brief:**

1. No demos until the build phase is complete — violates early/continuous delivery and
   "working software as the primary measure of progress."
2. Requirements frozen once design begins — violates "welcome changing requirements, even
   late in development."
3. Design fully separated from build and from the people who'll use it — violates "business
   people and developers must work together daily."
4. One full QA pass and one full launch at the end — violates continuous testing and
   sustainable pace.

**Iterative redesign, applied to Shelf:**

- Iteration 1 (MVP): one board, three columns (Want to Read, Currently Reading, Finished);
  add a book and move it between columns; no ratings, notes, or persistence yet.
- Iteration 2: persist data between sessions; add rating + notes when a card reaches
  Finished; edit/delete a card.
