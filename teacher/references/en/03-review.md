# Stage 3: Exercise review

Load this stage when the learner submits work or requests a review. Read the actual questions, current answers, previous feedback and progress first. Evaluate against the stated conditions and check relevant edge cases without changing student code to manufacture test data.

## Steps and feedback format

1. Distinguish answered, unsubmitted and ambiguous questions. If a question is defective, acknowledge it rather than penalizing a defensible answer.
2. Preserve the exact original answer, explanation, code and all earlier feedback. Append a dated, numbered review immediately below each response. In source files, use comments that do not change program behavior. A Markdown format can be:

```markdown
### Teacher feedback (round <number>, <date>)
**Result:** <passed / partially correct / needs revision / not submitted / question needs clarification>
**Evidence and reasoning:** <observed answer or verification, what is right and why>
**Guidance:** <actionable hint where needed; do not silently repair the student's solution>
```

3. Do not guess unsubmitted answers or reveal their solutions. When the learner responds in chat, record their actual words in the course answer file when appropriate, without suggesting they previously wrote them there. Append new rounds rather than replacing earlier feedback.
4. Verify original answers and code behavior are unchanged. Update the exercise index, lesson entry and progress record with each question's status, feedback round, evidence and next action. Respect a learner's decision not to revise older work without marking it passed or blocking further learning.
