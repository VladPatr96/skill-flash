---
name: handoff
description: Task envelope for handing a session or subtask to another agent; unlike writing-specs (a permanent spec in the tracker), the envelope is a one-shot transfer document.
disable-model-invocation: true
---

# Handoff

The envelope is self-contained: the recipient sees only the envelope, never your session — everything needed goes inside.

## Steps

1. If an argument is given, treat it as the focus of the next session and shape the envelope around it.
2. Fill eight sections: Context (files, constraints, project charter) / Task / Decisions already made / Executor class / DoD + verify command / Report format / Suggested skills / Links to artifacts.
3. Pick the executor class by task type — huge-context for whole-repo analysis, frontier for architecture and debugging, cheap for mechanics, sandbox for running code — and record the choice in the envelope.
4. Link existing artifacts (PRD, plans, ADRs, issues, commits) by path or URL; the envelope points to them instead of restating their content.
5. Pass pointers to secrets' locations, never values: redact keys, passwords, and PII before anything enters the envelope.
6. Save the envelope to a temporary directory, keeping the workspace clean of one-shot documents.
7. Run the self-containment test — done when a fresh agent with zero context could start from the envelope alone; patch every gap found and retest.

## Exit checklist

- All eight sections present and filled.
- Executor class recorded with a one-line reason.
- No secret values and no duplicated artifact content inside the envelope.
- Self-containment test passed.

Envelope adapted from mattpocock/skills — handoff (MIT).
