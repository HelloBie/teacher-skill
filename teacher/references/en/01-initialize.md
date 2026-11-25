# Stage 1: Course initialization

Use this stage when creating a course or adjusting its syllabus at the learner's request. Follow the learner's subject, teaching language, preferences and any applicable workspace conventions. Do not impose a fixed number of lessons or a timetable.

## Steps

1. Inspect the workspace and user context; decide whether to start a new course or reuse an existing one. Determine the subject, goal, background, teaching language and constraints; state reasonable assumptions where details are missing.
2. Create or update a course entry, syllabus and progress record in the selected workspace, adapting the structure and depth to the subject.
3. Verify lesson numbering, content and links. If the learner asked only for a plan, deliver it and wait. If they asked to start learning, load the teaching stage after planning.

## Default course layout

```text
<course>/
  README.md                 # Course entry and links
  docs/
    course-plan.md          # Goals, syllabus and teaching conventions
    progress.md             # Actual learning progress and next action
  lessons/
    lesson_01/
      README.md             # Lesson entry
      lesson_01.md          # Substantive notes for a taught part
      questions.md          # Real classroom questions, when they occur
      summary.md            # After all parts of this lesson are taught
      exercises/
        EXERCISES.md        # Exercise index
        part_01.md          # Questions and answer spaces
  exams/                    # Created as needed for the final assessment
```

These are defaults, not a requirement to rename existing files. Adapt names to the learner's teaching language, keep links consistent and preserve existing student work. Create materials as they become relevant, not empty notes presented as completed teaching. Keep each lesson's questions and answers in its own exercise folder. Do not require a software project or Git repository for non-programming subjects.

## Course plan

Record the direction, known background, target capability, assumptions and prerequisites; distinguish stated experience from unverified mastery. Describe scope, stages, learning goals and observable assessment criteria. Number lessons, state the actual total, and give each title, core topics, prerequisites, intended outcomes and practice or evaluation. Document the teaching and review conventions and the learner's explicit preferences. Include a final assessment based on the syllabus and taught material after the entire course has been taught. Update total counts and links when plans change; preserve teaching history.

## Progress record

Create the record during initialization and update it after teaching, questions, submissions, review, changes in order, pauses, summaries and final assessment. Include:

- Course, total lessons, current lesson and part, current phase, last taught content, next action and links.
- Learner background, goals, instructional language and, separately where relevant, the language being studied; record unknowns as unknown.
- Lesson or module progress, evidence and links; distinguish planned, teaching, taught, assigned, unsubmitted, submitted, reviewed, needs revision and passed where applicable.
- Per-question results and feedback links, actual questions and summaries, and exam status: not started, preparing, assigned, submitted, reviewed or passed as supported by evidence.

Teaching a lesson, issuing an exercise or running a template does not demonstrate mastery. Do not repeatedly require old corrections that the learner has declined, and do not mark them passed. Verify links and the correspondence between records and actual files.
