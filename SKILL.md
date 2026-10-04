---
name: notebooklm-incremental-progress-skill
description: Create and maintain NotebookLM progress briefings, notes, audio and video from current evidence. Use for an initial progress briefing, a new meaningful round, or continuation of a long running project or opportunity campaign. Reuse the same notebook, conversation and progress note; refresh relevant sources; explain recent outcomes and remaining work without setup, methods, old failures or repeated completed tasks.
---

# NotebookLM Incremental Progress

## Result

Maintain one current progress note for the real project. Produce the requested audio or video about recent meaningful outcomes, the current position, and what remains. Keep notebook selection, evidence reconciliation, prompts, technical incidents and production bookkeeping out of the media.

Apply the user's current scope, language, formats, count and length. Infer missing preferences from the current project and its latest direct user instructions. Use a factual briefing in the user's language when no preference exists. Never inflate a small update to fill a long duration.

## 1. Bind continuity once

1. Recover the exact project and existing notebook ID from the current task, linked original conversation, canonical project record or prior handoff. Verify the notebook belongs to the correct account and project.
2. Reuse that ID on every subsequent operation. Do not search for a similar notebook each round, create a duplicate because a lookup failed, or rename the established notebook. If no binding exists, list once and match the exact project identity and relevant sources. Create a notebook only when there is no canonical one, or when the user explicitly requests a separate notebook.
3. Recover the progress-note ID, conversation ID, current source IDs and last verified media IDs. Keep these bindings and the last covered event horizon in the durable project context used by the caller. Do not create a duplicate tracker or continuity system merely for this skill.
4. Use explicit full notebook IDs for every operation. Avoid changing the shared CLI's active context. Verify that each response and mutation read-back belongs to the bound notebook; a shared-context race must not redirect the next step. Serialize mutations to the same note or artifact and re-read its latest state before updating it. An access/authentication error is not proof that the notebook is missing; recover access before considering a replacement. If access remains unavailable, preserve the binding and report the exact gap.

## 2. Refresh only sources that establish current progress

Read the previous progress note and the newly relevant part of the original conversation. Check later events, direct user corrections and current primary records before classifying anything as remaining work.

Build an internal table for every in-scope item: exact identity, latest event/date, verified state, change since the last covered round, remaining step, responsible party, and evidence. Include all items in an explicit requested population; report an unavailable slice instead of silently sampling.

Classify available material:

- **Current evidence:** latest native records, receipts, messages, accepted decisions and current canonical reports. Check their date, meaning and coverage.
- **History:** earlier facts needed to understand a meaningful change. Later evidence supersedes an old plan or status.
- **Production context:** agent instructions, prompts, setup, tool errors, audit chatter, strategy scaffolding, old failed attempts and generated commentary. Never select this as media input.

For each relevant URL or Drive source, probe its actual refresh support and staleness, refresh when appropriate, and read back the ingested text. A ready status or new timestamp alone does not prove updated content. Uploaded files and pasted text are snapshots; compare them with their actual current origin. Do not append conflicting current states to an old snapshot and let the generator choose between them.

Reuse a ready snapshot when its substantive content is unchanged. When a snapshot has changed, add one corrected, current briefing source, read it back, and select its exact ID for this round. Retain the older source as history without selecting it. Check after an uncertain add before retrying, so an accepted request cannot create duplicate sources. Use a stable canonical Drive source when supported; do not create per-round copies merely to avoid refreshing it.

Select an explicit allowlist of relevant, ready source IDs for chat and generation. Never default to every source in a notebook containing instructions or stale snapshots. Keep evidence pointers internally; spoken output should explain facts directly.

## 3. Form the meaningful update

Compare actual facts with the last covered round, not with source counts, file modification times or the previous agent's completion claims.

Include:

- newly completed, submitted, accepted, delivered or otherwise evidenced outcomes, with their actual meaning;
- material changes to status, quantities, amounts, deadlines, dependencies or decisions;
- active remaining work, the next concrete step and who owes it;
- a brief current total or baseline only when it helps understand the change.

Remove completed actions from the remaining-action list. Omit unchanged old completions, resolved mistakes and production incidents. Preserve a newly completed outcome in this round even though it is now done. Do not turn an unanswered outbound message into another owed follow-up. A passed deadline, new requirement or corrected consequential fact can be meaningful without a new completion.

Keep prepared, attempted, submitted, received, admitted, awarded, paid and delivered distinct when relevant. Count distinct outcomes by exact entity; a replacement submission is not automatically a new opportunity. Keep budgets, requested funding, granted money, credits and actual receipts separate. State a missing substantive outcome directly without narrating the agent's failure to obtain it.

Compare the note with its last verified note horizon and each requested medium with its own last verified media horizon. If there is no meaningful change and every requested output is already verified, reuse the last briefing and media. Do not create a new source, duplicate note, initial chat or generation. This no-change rule never skips outstanding media merely because the note was saved: resume the bound processing or failed artifact, or complete the already-authorized missing output. If the user explicitly requests a fresh unchanged briefing, produce the current position without invented progress. Never interrupt the underlying campaign merely to make an update; perform this skill at a requested checkpoint or after a meaningful completed round.

## 4. Start one grounded conversation and maintain one note

On first use, ask the notebook to synthesize the current position from the selected sources: recent outcomes, remaining work, concrete next steps, important dates and exact state meanings. Validate the answer against the evidence before saving it. Create one clearly titled progress note containing the corrected briefing. Read the note back and retain its ID.

On subsequent meaningful rounds, continue the bound conversation when supported, inspect its latest state, and update the same progress note by ID. Do not create another initial conversation or another note. If the conversation is absent, ask normally and bind the returned ID; never clear existing history as a shortcut. If only the note is truly missing, create it once and record the new binding.

Write the note for the reader: the current cutoff, recent substantive changes, current position, remaining actions and dates. Keep internal bindings, validation notes and production state in the durable project context, outside the note's reader-facing body and outside generation sources.

## 5. Generate only the requested media

Build a separate generator prompt from the validated briefing. Do not paste this skill, raw sessions, an audit, an internal ledger or the source inventory into the generator. Use only the approved public fields: subject, cutoff, current position, recent changes, remaining actions, responsible parties, meaningful dates, amounts and distinctions.

Use this instruction, tailored with the actual facts and requested language:

> Start immediately with the latest meaningful progress. Explain what changed in the latest rounds, the current position, and what remains to be completed. Preserve the supplied names, numbers, amounts, dates and state meanings. Describe completed actions as completed and omit them from the remaining-action list. Give concrete next steps and who owes them. Mention old completed work only as a short baseline necessary to understand the latest change. Explain uncertainty only where it changes the substantive position. Keep narration focused on the actual project. Omit greetings, host banter, motivational language, metaphors, generic tutorials, source narration, NotebookLM, setup, prompting, research methods, technical incidents and resolved mistakes. End with the remaining priorities. Do not invent results, causes, dates or promises.

For video, use readable labels, grounded comparisons and timelines. Show only evidenced relationships and figures. Avoid invented screenshots or events. For multiple artifacts, assign distinct coverage and preserve the requested count; do not repeat the same full briefing in each one.

Inspect existing artifacts before generation. If an artifact for the same validated content, language, format and coverage is already processing, resume its ID. If a verified matching artifact exists, reuse it unless the user requests a new one. Before submitting, retain the existing artifact IDs, request start time, selected source IDs and exact prompt fingerprint in the caller's durable project context. Bind the returned full task ID immediately. After a response timeout without an ID, compare new provider artifacts with that baseline, creation time and available generation prompt/source metadata. Bind only an unambiguous match. If several candidates remain, preserve that exact uncertainty and do not submit another generation. Bind each new artifact to its selected sources, content fingerprint, prompt, coverage and actual provider state in the durable project context. Do not advance the last media-covered horizon until that artifact passes content and playback review.

## 6. Verify the actual result and close

Poll the exact artifact; accepted, queued or processing is not delivery. Retry a failed artifact through a supported operation after diagnosing its actual error. Do not generate another copy after an ambiguous timeout without checking the original request.

Inspect the completed transcript or spoken content against the final briefing. Check every material outcome, state, amount, date and remaining step; verify that setup, methods, stale tasks and resolved mistakes are absent. Check video labels and visuals too. Correct an evidenced defect and verify the replacement before calling it ready. Do not make a flawless prompt stand in for a reviewed generated artifact.

Open the exact native player and confirm it plays. When an export is requested, open the actual exported file and verify its format and contents. Use an existing approved file when one suffices; otherwise create only the minimum file inherently needed for an authorized export or transcription. Do not write scratch logs or trackers.

Update the same note and durable project context with the verified state. Preserve separate note, source and media horizons so a saved note or still-processing artifact cannot make unfinished media disappear on the next run. Finish with a concise outcome, links to the notebook/artifacts, the latest meaningful changes and remaining substantive items. Report an exact verification gap when one cannot be closed. Do not claim that future generations will always be correct.

## Supported route and CLI examples

Prefer the existing authenticated NotebookLM connector, CLI or SDK. Probe the installed version, help and actual response shape before relying on a flag or field; the CLI and system Python can use different package versions. Use the in-app Browser for authentication or final native playback when needed. Keep input and diagnostics in memory.

The following commands are supported by notebooklm-py 0.8.2; adapt only after inspecting the installed contract. Replace placeholders with bound full IDs and reviewed content. These examples are operations, not a script to execute blindly.

```sh
notebooklm --version
notebooklm list --json
notebooklm source list -n NOTEBOOK_ID --json
notebooklm source fulltext SOURCE_ID -n NOTEBOOK_ID --json
notebooklm source stale SOURCE_ID -n NOTEBOOK_ID --json
notebooklm source refresh SOURCE_ID -n NOTEBOOK_ID --json
notebooklm source add "REVIEWED_CURRENT_BRIEFING" --type text --title "Current progress — CUTOFF" -n NOTEBOOK_ID --json
notebooklm ask "GROUNDED_PROGRESS_QUESTION" -n NOTEBOOK_ID -s CURRENT_SOURCE_ID --json
notebooklm ask "LATEST_MEANINGFUL_UPDATE" -n NOTEBOOK_ID -c CONVERSATION_ID -s CURRENT_SOURCE_ID --json
notebooklm note list -n NOTEBOOK_ID --json
notebooklm note create "VALIDATED_PROGRESS_BRIEFING" -t "Progress — PROJECT" -n NOTEBOOK_ID --json
notebooklm note save NOTE_ID --content "VALIDATED_UPDATED_BRIEFING" -n NOTEBOOK_ID --json
notebooklm note get NOTE_ID -n NOTEBOOK_ID --json
notebooklm artifact list -n NOTEBOOK_ID --json
notebooklm generate audio "REVIEWED_PROGRESS_PROMPT" -n NOTEBOOK_ID -s CURRENT_SOURCE_ID --format deep-dive --length long --language LANGUAGE --no-wait --json
notebooklm generate video "REVIEWED_PROGRESS_PROMPT" -n NOTEBOOK_ID -s CURRENT_SOURCE_ID --format explainer --language LANGUAGE --no-wait --json
notebooklm artifact poll ARTIFACT_ID -n NOTEBOOK_ID --json
```

`ask --new` deletes the existing server conversation in this CLI version. Never use it for incremental continuity. Never run broad source cleanup or delete historical artifacts as part of a progress update. Before external release, review the exact briefing, prompt, and generated content for factual accuracy, audience fit, and exclusion of operational context before calling the result ready.
