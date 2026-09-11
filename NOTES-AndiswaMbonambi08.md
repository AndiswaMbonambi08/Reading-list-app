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

* Iteration 1 (MVP): one board, three columns (Want to Read, Currently Reading, Finished);
add a book and move it between columns; no ratings, notes, or persistence yet.
* Iteration 2: persist data between sessions; add rating + notes when a card reaches
Finished; edit/delete a card.

## Assignment 2.2

### Question 1 — Roles, solo and shared

For TrackFlow, the roles get assigned in class since it's cohort-wide, so I don't have a fixed answer yet. My guess is I'll end up in a Dev Team seat by default, with Product Owner and Scrum Master responsibilities split or rotated across the group.

For Shelf, I'm all three roles, and the one I expect to neglect first is Product Owner style discipline, specifically writing a real Definition of Ready before pulling something into a sprint. When you're also the developer, it's tempting to skip straight to building whatever feels interesting that session and skip stating acceptance criteria, since there's no one else who needs the item spelled out. The concrete habit that would stop this: before moving any backlog item into a sprint backlog, I write its Definition of Ready check as an actual short checklist against it, even if it takes two minutes. If I can't check every box, it doesn't move.

### Question 2 — Definition of Ready, Definition of Done

Writing this for Boards \& Cards rather than Auth, since Auth is out of scope for Iteration 1 per my Assignment 2.1 redesign. Boards \& Cards is the epic I'm actually building first.

Definition of Ready (Boards \& Cards):

* The item has a one line user facing description of the interaction, for example "user can add a book card to Want to Read".
* It lists two or three acceptance criteria stated as testable behaviour, not vague goals.
* It has no unresolved dependency on Auth or persistence, since neither exists yet in Iteration 1.
* The screen or component it lives in is named.
* It's small enough to finish in one solo working session, roughly under three hours.

Definition of Done (Boards \& Cards):

* The board renders the three fixed columns: Want to Read, Currently Reading, Finished.
* A card can be added with title and author and appears in the correct column.
* A card can be moved between columns and the UI reflects the move immediately.
* I've manually walked through add, move, move at least once without errors.
* No console errors during that walkthrough.
* The code is committed to main and runs locally without build errors.

### Question 3 — The artifact most at risk

Of Product Backlog, Sprint Backlog and Increment, Sprint Backlog is the one most at risk of being skipped or faked in a solo daily cadence project like Shelf. The Product Backlog is just a running list, easy to keep honest since it's low stakes to add or remove an item. The Increment happens almost automatically, since working solo means whatever I build each session is the increment by definition.

The Sprint Backlog is different because it's a commitment made in advance, and without a partner checking whether I stuck to it, it's easy to quietly swap items mid sprint and then write the sprint backlog after the fact to match whatever I actually did. The real cost of skipping it isn't that the work doesn't get done. It's that I lose the one artifact that would tell me whether my planning and estimates were any good. Without a genuine sprint backlog, there's no way to notice scope creep while it's happening, and no learning signal for the next planning session.



### NOTES.md Updates

1. The role I said I'd neglect first was Product Owner style discipline, specifically writing a real Definition of Ready before pulling something into a sprint. Actually doing Part 2 confirmed rather than changed that. It was genuinely tempting to skip straight to listing backlog items I found interesting and skip writing acceptance criteria for the Boards \& Cards items until I forced myself to check each one against the Definition of Ready.
2. Yes. The Definition of Ready blocked every Auth item from Sprint 1, even though Auth is listed first in my epics and instinctively felt like it should come first. It also blocked persistence and the rating and notes feature, both of which I expected to sneak into Sprint 1 since they felt small. Writing the Definition of Ready down made it obvious they all depend on something that doesn't exist yet in Iteration 1.

## Assignment 2.3

### Question 1 - Choosing a view

Board will be my Daily app's primary view day to day. Shelf data model already is Board > Column >Card, So basically the Board view in Asana just mirrors the app: I open it, see Want to Read / Currently Reading / Finished as columns, and drag cards across as I read. That's the daily-use motion.

List still earns a place for anything Board hides: bulk-editing custom fields across many cards at once, or scanning every backlog item as a flat, sortable table when I'm grooming the backlog rather than working through it.

Timeline is for iteration planning, not daily work. When I'm laying Iteration 1 and Iteration 2 out against each other, or checking that a dependency (say, persistence landing before ratings/notes can work) actually lines up in time, Timeline shows that sequencing in a way Board can't.

### Question 2 - Custom fields, deliberately

* **Epic** (Auth / Boards \& Cards / Book Details \& Notes / Search \& Filter / Reminders) - lets me filter the project down to one epic and see at a glance how much of it is done, so I know which epic to pull the next card from.
* **Iteration** (Iteration 1 / Iteration 2 / Backlog) - the filter that answers "what's actually in scope this week" versus everything else sitting in the backlog for later.
* **Priority** (High / Medium / Low) - decides what I pull in next whenever I have slack time inside an iteration instead of working top-to-bottom by instinct.
* **Effort** (S / M / L) - a capacity check before I commit a card to an iteration; if Iteration 1's cards are mostly L, that's a signal I've overcommitted a one-week MVP.

Each one exists because it changes a decision I actually make. I left Story Points off on purpose: Shelf is solo with irregular sessions, so point estimation for velocity tracking has nobody to report to and nothing to calibrate against. Effort as a rough S/M/L sizing does the one job I need (sanity-check iteration scope) without the overhead.

### Question 3 - Tag or field?

**Tag:** something like "learning" or "spike", a loose, cross-cutting label for a card that's really about exploring or practicing something rather than shipping a feature. It's not specific to Shelf; I'd want the same tag on cards in other Bitcube assignments too.

**Field:** Iteration. It's structured, single-select, and only makes sense scoped to this one project.

If I swapped them:

* Iteration as a tag would lose the "exactly one value" constraint. A card could end up tagged both Iteration 1 and Iteration 2, and I couldn't group Board columns or build a clean iteration filter off something that isn't enforced to be single-valued.
* "Learning" as a custom field would get trapped inside the Shelf project. It wouldn't follow the card if I wanted to spot every learning-type task across Assignment 1.3, Assignment 2.2, and Shelf at once. I'd end up rebuilding the same field per project instead of reusing one tag across the whole workspace.



### NOTES.md Updates

1\. What the given backlog exercise revealed

Building QuickNotes first with status sections (Backlog, In Progress, Done) rather than epic sections is what made me confident sectioning Shelf by epic instead was the right call for a backlog view, status only matters once something is being worked, and Shelf's Product Backlog isn't there yet. QuickNotes also surfaced a mechanical thing I didn't expect: a tag has to actually be applied to at least one task before Asana will offer it as a filter option, which changed the order I did things in on the real project, tag or set the field first, filter second, not the other way round.



2\. Where Sprint 1 Backlog and reality disagreed

Nothing about which items belonged in Sprint 1 changed, the Definition of Ready check from Assignment 2.2 held up. What moving it into Asana did surface is how uneven the three Sprint 1 items are once Effort sits next to them in a column: "move a card between columns" clearly carries more real work than its one-line phrasing suggested, enough that it's the one item I broke into subtasks, while "add a book card with a title and author" and "see a board representing my whole shelf" are comparatively small. On paper the three read as roughly equivalent scope; side by side with an Effort field, they aren't.



3\. The field vs. tag call you almost got wrong

When I got to Task 9's saved filter, my first instinct was to solve it the same way as Task 5, tag the Sprint 1 items and filter by tag. That would have worked by accident, but it's the wrong mechanic for the same reason Question 3 argues Iteration should be a field: tags don't enforce one value, so nothing would stop a task from picking up both a "Sprint 1" tag and a "Sprint 2" tag later, and the filter would quietly start returning wrong results. Using the Iteration field instead means the filter can only ever be accurate.





#### \### Asana Projects



###### \- QuickNotes (practice): 

https://app.asana.com/1/1218293804888571/project/1218294161837579/list/1218296317073426



###### \- Shelf (Daily App): 

https://app.asana.com/1/1218293804888571/project/1218333052944223/list/1218333673620846



## Assignment 2.4

### Question 1 - Rewrite Sprint 1 as real user stories

1. As a returning reader, I want to see a board representing my whole shelf so that I can tell at a glance what I'm reading, what's next, and what I've finished without scanning a flat list.

2\. As a reader who just picked up a new book, I want to add a book card with a title and author so that I can start tracking it immediately.

3\. As a reader progressing through a book, I want to move a card between columns (Want to Read, Currently Reading, Finished) so that my shelf reflects where I actually am with each book.

4\. As a reader who made a mistake or learned new details, I want to edit a card's title or   author after adding it so that my shelf stays accurate.

5\. As a reader who added something by mistake or no longer cares to track it, I want to delete a card so that my shelf only shows books I'm actually tracking.





### Question 2 - Acceptance criteria

1. See the board: Three columns render with the labels Want to Read, Currently Reading, Finished, in that order. An empty column shows a visible empty state rather than blank space. All existing cards appear in the correct column on load.

2\. Add a card: A visible "add card" action exists on at least the Want to Read column. Submitting with a title and author creates a card showing both fields. Submitting with an empty title is rejected with a visible message, no blank card is created.

3\. Move a card: A card can be dragged (or moved via an equivalent control) from any column to any other column. The card's column position updates immediately without a page reload. The card retains its title/author after the move.

4\. Edit a card: An edit action is reachable from the card. Changing the title or author and confirming updates the visible card text immediately. Cancelling an edit leaves the original values unchanged.

5\. Delete a card: A delete action is reachable from the card. Confirming removes the card from the board immediately. The action requires a confirmation step (e.g. a confirm dialog) so an accidental click can't silently delete.



### Question 3 - INVEST check

Picking story 3 (move a card between columns):



Independent — fails. It can't be built or demoed without stories 1 (the board existing) and 2 (a card existing to move), so it's not truly independent of the rest of Sprint 1.

Negotiable — passes. Whether it's drag-and-drop or a dropdown/button-based move is still an open implementation choice.

Valuable — passes. This is the core loop of the whole app.

Estimable — passes, now that it's broken into the 3 subtasks from 2.3 (drag handler, persist state, handle invalid drops).

Small — borderline fail. Needing 3 subtasks to even estimate it is itself a sign it's carrying more than one story's worth of work.

Testable — passes, per the acceptance criteria above.



It fails Independent structurally (that's fine, sequencing handles it) but the Small failure is the one worth fixing: I'd split "handle invalid drop targets" out into its own follow-up story instead of a subtask, since it's really an edge-case/robustness concern rather than core to "move a card." That shrinks story 3 down to just drag + persist, and moves error handling to a Sprint 2 candidate.



### Question 4 - Estimating alone, again



Using "add a book card" as the reference story (2 points, a simple form + list insert):



Story: See the board  

Points: 3

Why: More structural than it sounds, three columns, empty states, initial load logic



Story: Add a book card

Points: 2

Why: Reference story



Story: Move a card between columns

Points: 5

Why: The 3-subtask breakdown from 2.3 makes this the biggest item by a clear margin



Story: Edit a card

Points: 3

Why: Similar shape to add, plus needing to locate/update the right card



Story: Delete a card

Points: 1

Why: Smallest, removal plus a confirm step

&#x20;                 

The surprise: "move a card" felt like a Medium effort item back in Assignment 2.3 (that's literally what I tagged it), but once it's decomposed into real subtasks it's the biggest story in the sprint at 5 points, more than double the reference story. Breaking it down revealed complexity the one-line phrasing hid.



### NOTES.md Updates-Assignment 2.4



NOTES.md Updates



1\. What changed between backlog phrase and real story

"Delete a card" looked like the smallest, most obvious item in Sprint 1, a one-line phrase with an equally obvious meaning. Writing the full story ("As a reader who added something by mistake or no longer cares to track it, I want to delete a card so that my shelf only shows books I'm actually tracking") forced me to name why someone deletes a card, and that surfaced two different reasons: a mistake versus genuinely losing interest. That distinction is what led to the acceptance criteria requiring a confirmation step, a raw backlog phrase like "user can delete a note" gives no reason to think about accidental deletion at all, it just reads as a CRUD checkbox.



2\. The retro, from the inside

\[To be filled in after TrackFlow's mock sprint retro in class, this needs an actual thing someone in the group said or a pattern that came up live, not something I can draft in advance.]



3\. Estimating with real stories vs. rough backlog items

Less confident, in a useful way. In Assignment 2.2 I estimated Boards \& Cards items as roughly equivalent effort just from their one-line phrasing. With real acceptance criteria in front of me in Assignment 2.4, "move a card between columns" clearly needed 5 points against a 2-point reference story, more than double, once I could see the actual conditions (drag handling, state persistence, invalid drop targets) rather than a short sentence. The estimates feel more trustworthy now specifically because they were harder to produce, I couldn't estimate from a vibe, I had to check the story against something concrete.





