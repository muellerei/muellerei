## Patrick Müller

Tools I needed and nobody had built.

Writing code since 1985, paid for it since around 1990: Fortran77, Oracle
Forms, LAMP, Angular, and whatever the current generation calls itself.
Long enough to tell what will still be here in ten years from what is
merely loud right now.

Programming is a puzzle and a craft at the same time: solve the problem,
then make the code simpler than the problem was. I find a problem, I build
a tool, lately in Python and TypeScript, on the command line and against
whatever API is in the way.

### What I hold to

**Boring beats clever.** Readable code beats a smart abstraction every
time. The clever version is a debt someone pays later, usually me.

**Context decides.** A prototype may take shortcuts. Something people
depend on may not. Knowing which one you are writing is most of the job.

**No dependency without a reason.** Every package is a promise someone
else has to keep. Standards outlive vendors.

**A view must not be able to disagree with its source.** Anything derived
gets recomputed, never kept by hand in a second place. Two versions of
the truth start drifting the day you write the second one.

**Write down why, not just what.** A decision that took an afternoon to
reach should not take an afternoon to reconstruct.

### Projects

**[logseq-cli](https://github.com/muellerei/logseq-cli)**: read and write a
Logseq graph from a shell or an AI agent. Python, `click`, no vendor
coupling. Verified writes, because the API answers a failed one with
HTTP 200 and `null`.

**[roadmapper](https://github.com/muellerei/roadmapper)**: derive a Notion
roadmap from GitLab epics and milestones. One way only: the board is a view,
so it cannot drift from the tracker. Progress is a sum over the issue tree,
which is the one thing a field mapping cannot do. TypeScript, two
dependencies, one command for cron.

#### Claude Code mods

All TypeScript, no network, and none of them writes files.

- **[task-line](https://github.com/muellerei/task-line)**: one line per task
  list above the prompt, with the current task, a progress bar and the count.
  It reads the lists Claude keeps and creates none.
- **[enable-todo-tools](https://github.com/muellerei/enable-todo-tools)**:
  newer models leave Claude's todo tools out, so task-line would have nothing
  to show. This sets `CLAUDE_CODE_ENABLE_TODO_TOOLS=1` at session start.
- **[sweet-spot](https://github.com/muellerei/sweet-spot)**: hands a long
  session over before the context gets too big, at a pause and never mid-turn.
  The 200k default is measured: most of the cost in real sessions came from
  calls above it.
- **[diff-fold](https://github.com/muellerei/diff-fold)**: one line per file
  instead of the diff under a finished edit. Small diffs and changes to
  secrets, CI or Claude's own instructions stay in full, because a summary
  would hide what they do.

---

*Germany. Off the keyboard: a gravel bike, daily, non-negotiable.*
