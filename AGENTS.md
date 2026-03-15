# AGENTS.md

## Purpose
This repo is an MVP idea-workbench for Amit.
Use it to turn rough ideas into clean business-style artifacts:
- presentations (highest priority)
- documents
- spreadsheets
- simple diagrams

The goal is speed, clarity, and reusability.

## Default operating mode
Work in this order unless Amit asks otherwise:
1. Understand the goal
2. Ask only the minimum clarifying questions
3. Create a short outline
4. Wait for approval if the task is large
5. Create the source files
6. Create the final artifact if requested
7. Summarize what was created and what should be reviewed next

## Output priorities
Default output mix:
- 70% presentation
- 20% document
- 10% spreadsheet

## Audience detection
Always identify the target audience early.
Use one of these defaults unless Amit says otherwise:
- technical
- management
- director / executive

If unclear, ask one short question:
"Who is this for: technical, management, or executive?"

## Style rules
Default style:
- high-quality business style
- plain
- blue-led visual language
- sparse slides
- strong structure
- high-level wording first
- avoid clutter

For presentations:
- dark or light theme is allowed, but prefer a clean blue-led business feel
- use a limited palette
- keep one idea per slide where possible
- avoid dense text
- use speaker notes for detail

For documents:
- start with executive summary
- use short sections
- use bullets where possible
- avoid long walls of text

For spreadsheets:
- create only when structure, comparison, tracking, or calculation is needed
- prefer clear tabs and simple headers
- keep formulas readable

## Source of truth
Prefer text-first source files:
- presentations: markdown, marp, notes, metadata
- documents: markdown first, export later if needed
- spreadsheets: csv, yaml, or simple tabular specs first, xlsx later if needed
- diagrams: mermaid first when possible

Do not treat binary files as the main editable source unless Amit explicitly asks.

## File naming
Use:
- lowercase
- underscores
- short but descriptive names

Examples:
- proposal_ai_enablement_slides.md
- proposal_ai_enablement_notes.md
- proposal_ai_enablement_meta.yml

## Repo structure
Keep the repo simple.

Recommended folders:
- ideas/
- tasks/
- presentations/
- documents/
- spreadsheets/
- diagrams/
- templates/
- exports/

## Task handling
If Amit gives a rough idea:
1. convert it into a task file in tasks/
2. propose a short outline
3. create the source artifact in the right folder
4. create exports only when asked

Each task file should contain:
- title
- date
- goal
- audience
- requested output
- status
- next step

## Presentation defaults
When making a presentation:
1. start with a 5 to 8 slide outline
2. confirm the audience
3. keep the title and key message clear
4. keep slides high-level
5. add speaker notes
6. export to pptx only if requested

Suggested slide flow:
- title
- problem / opportunity
- context
- proposed idea
- benefits
- risks / assumptions
- next steps
- ask / decision

## Document defaults
When making a document:
- start with purpose
- include executive summary
- add recommendation
- keep sections practical
- include next actions

## Spreadsheet defaults
When making a spreadsheet:
- define the purpose first
- prefer a simple schema
- add only useful columns
- avoid overengineering

## Diagram defaults
Prefer:
1. mermaid
2. simple block diagrams
3. AWS diagrams only when needed

If the diagram is complex, create the logical structure first before styling.

## Review mode
When Amit wants fast review:
- provide a short summary first
- then point to the file path
- then suggest exactly what to review:
  - structure
  - tone
  - audience fit
  - visual style
  - completeness

## Safety / limits
Do not:
- invent confidential facts
- overcomplicate the repo
- create too many files for small tasks
- use flashy design by default
- create exports before the source is clear

## MVP rule
For the first week:
- optimize for speed
- keep the repo small
- prove the workflow works
- do not build a giant framework too early

## Week 1 success criteria
This MVP is successful if Amit can do all of the following:
1. speak or type a rough idea
2. get a clean outline
3. get a draft presentation or document quickly
4. review it easily
5. request revisions
6. get a final export when needed
