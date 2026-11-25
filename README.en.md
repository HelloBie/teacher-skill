# Teacher

[中文](README.md) | English

[![skills.sh](https://skills.sh/b/HelloBie/teacher-skill)](https://skills.sh/HelloBie/teacher-skill/teacher)

**Turn a learning goal into a course you can continue at your own pace.**

Teacher is a general-purpose teaching skill for AI assistants that support the `SKILL.md` format. Describe what you want to learn, and Teacher can create a tailored syllabus, teach with examples and guided practice, provide exercises and feedback, and save course materials and progress in your workspace.

It is not limited to programming. Languages, design, mathematics, writing, product skills and professional development can all use the same workflow, with examples and exercises adapted to the subject.

> This project provides instructions and file conventions for an AI assistant. It is not a standalone teaching application or a collection of prewritten courses. Results depend on the assistant, model, available tools and subject matter.

## Features

- **Multilingual teaching:** Use the requested instructional language, or the language the learner is currently using. The language of instruction can differ from the language being studied.
- **Goal-oriented planning:** Build a syllabus around the learner's goals, background, prerequisites and expected outcomes.
- **Teach before testing:** Explain what a concept is, when and how to use it, and the tradeoffs of comparable approaches before guided practice and exercises.
- **Persistent progress:** Track the syllabus, lessons, individual exercise feedback and next steps, distinguishing instruction, submitted work and demonstrated mastery.
- **Preserved answers:** Keep the learner's original responses and code, with feedback appended below each answer. Record unanswered or ambiguous questions accurately.
- **Lesson summaries:** Consolidate each completed lesson's explanations, actual classroom questions and review points into one document.
- **Final self-assessment:** After all course material has been taught, design a comprehensive assessment from the syllabus and actual lessons, then review the submitted work.
- **Progressive loading:** Load detailed instructions only when entering the relevant initialization, teaching, review, summary or final-assessment stage.

## Installation

### Install with the Skills CLI

Node.js and npm are required. Run:

```bash
npx skills add HelloBie/teacher-skill --skill teacher
```

Choose the assistant when prompted. Installation targets the current project by default. Add `-g` for a global installation after checking for an existing skill with the same name. See [Teacher on Skills.sh](https://skills.sh/HelloBie/teacher-skill/teacher).

### Install manually for Codex

Copy the repository's `teacher` directory into the Codex skills directory. The commands use `$CODEX_HOME`, falling back to `~/.codex` when it is unset.

```bash
git clone https://github.com/HelloBie/teacher-skill.git
cd teacher-skill

SKILLS_DIR="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$SKILLS_DIR"

# Copy only when the destination does not already exist.
if [ ! -e "$SKILLS_DIR/teacher" ]; then
  cp -R teacher "$SKILLS_DIR/teacher"
else
  printf '%s\n' "A skill already exists at $SKILLS_DIR/teacher; inspect it first."
fi
```

Start a new Codex session and invoke `$teacher`. Whether an existing session immediately discovers a new skill depends on the client.

### Other assistants supporting `SKILL.md`

Place the entire `teacher/` directory in the assistant's skills directory, keeping the `references/` folder, and follow that assistant's instructions to enable it. Skill discovery, tool permissions and workspace access vary by product.

## Quick start

In a workspace suitable for course materials, ask a supported assistant:

```text
$teacher I want to learn data analysis systematically. I know basic Excel and
want to independently produce an analysis report. Please start with a syllabus
and an exercise plan.
```

When you request only a plan, Teacher prepares the syllabus first. Review it or request changes, then ask to start the first lesson. You can also start directly:

```text
$teacher I want to learn photography from scratch. Design a course and start
with the first lesson in English.
```

Specify a teaching language when needed—for example, “teach me Spanish in English.” Otherwise, Teacher follows the language you are using. Continue naturally:

```text
Continue the course.
I don't understand this part. Please use another example.
I finished the exercises. Please review them.
Pause the course.
```

When resuming, Teacher reads the existing syllabus and progress and continues with the current lesson's next untaught part. Learners can change the order or pace; unfinished earlier exercises are not automatically marked as passed.

## Teaching workflow

| Stage | What Teacher does | Main artifacts |
| --- | --- | --- |
| Course initialization | Design the syllabus around goals, background and constraints | Course plan and progress record |
| Teaching and exercises | Identify the lesson, explain and demonstrate concepts, guide practice, then assign exercises | Lesson notes, exercise index and answer files |
| Exercise review | Check submitted work, preserve original answers and append dated feedback | Per-question feedback and updated progress |
| Lesson summary | Consolidate all taught parts and real classroom questions after the lesson is complete | Lesson summary |
| Final assessment | Design a comprehensive self-test after the entire syllabus has been taught | Exam, answer files and feedback |

Detailed instructions and file requirements live in separate stage references. Instruction, exercise completion and assessment are tracked separately: a plan, assigned task or runnable template is not evidence of mastery.

## Course materials

A new course can use the structure below; existing workspace conventions take precedence. Names can be localized to the instructional language. Non-programming subjects do not require code files or a Git repository.

```text
<course>/
├── README.md
├── docs/
│   ├── course-plan.md
│   └── progress.md
├── lessons/
│   └── lesson_01/
│       ├── README.md
│       ├── lesson_01.md
│       ├── questions.md       # when actual questions are asked
│       ├── summary.md         # after all parts of the lesson are taught
│       └── exercises/
│           ├── EXERCISES.md
│           └── part_01.md
└── exams/                     # created as needed after the course is taught
    ├── README.md
    └── exam_01.md
```

Files are created as teaching progresses; lessons and answers are not filled in ahead of time. The final assessment is a self-test, not an official qualification.

## Skill structure

```text
teacher/
├── SKILL.md                    # Entry point, stage routing and shared rules
└── references/
    ├── 01-initialize.md        # Course initialization
    ├── 02-teach.md             # Teaching and exercises
    ├── 03-review.md            # Exercise review
    ├── 04-conclude.md          # Lesson summary
    ├── 05-final-exam.md        # Final assessment
    └── en/                     # English stage instructions
```

The entry point provides stage links in Chinese and English. Teacher loads the appropriate stage instructions and can deliver course materials in the learner's requested language. When modifying the skill, keep both language versions and stage links consistent, and avoid overwriting learners' answers or existing course materials.

## Scope and limitations

- Teacher organizes the learning process. Check authoritative sources where a topic involves changing information or high-stakes decisions.
- Learning records live in the assistant's accessible workspace. Decide which materials are suitable to share and avoid unintentionally publishing personal answers or sensitive information.
- Installing the skill does not automatically create a GitHub repository, publish material or send messages on your behalf; those actions require user authorization.

## Contributing

Issues and pull requests are welcome. Describe the scenario, expected behavior and actual result. For changes to course files, answer preservation or stage routing, explain how you verified them. The Codex `skill-creator` validator can check the skill format; also verify the reference links in `SKILL.md`.

## License

[MIT License](LICENSE).
