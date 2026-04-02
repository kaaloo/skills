# Memory import workflow

## Goal

Turn ChatGPT export material into good Letta memory, not maximal Letta memory.

## Default posture

Use proposal-first behavior.

1. List the archive.
2. Render the relevant conversation or range.
3. Read the markdown.
4. Separate durable facts from noise.
5. Propose memory updates.
6. Apply only after review.

## Good candidates for active Letta memory

Import into active memory when the fact is:

- stable over time
- useful in future collaboration
- clearly stated or repeatedly reinforced
- not sensitive beyond what is needed for the working relationship

Examples:
- name
- long-lived response preferences
- recurring project context
- stable tool or workflow preferences
- durable personal notes the user clearly wants remembered

## Better fits for audit/import files

Keep information in an audit/import file when it is:

- historical and possibly stale
- weakly supported
- sensitive and unnecessary for future work
- a one-off task or temporary emotional state
- too detailed for pinned system memory

Examples:
- old job titles that may no longer be true
- transient plans for the week
- full raw transcript excerpts
- account metadata that is not needed day to day

## Parallel review guidance

If the archive is large:

- ask how aggressive the mining should be
- split review by conversation or shard
- use cheap subagents for reading and synthesis
- use `render-range.py` for batch preparation when helpful
- merge only high-confidence candidates into the final proposal

## Useful output pattern

When reporting back after reviewing rendered markdown, structure the result as:

1. **Explicit saved memory found**
2. **Durable preferences**
3. **Project/work context**
4. **Historical or uncertain facts**
5. **Proposed Letta memory updates**
