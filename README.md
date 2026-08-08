# Technical Book Tutor

A modular AI tutoring skill designed to turn technical books into **interactive, deeply understandable learning experiences**.

Instead of simply summarizing a book, Technical Book Tutor teaches each excerpt through:

**Intuition → Mathematics → Algorithm → Code → Example → Debugging → Application → Practice**

It is designed especially for technical subjects such as **Machine Learning, Deep Learning, Computer Vision, Digital Image Processing, CUDA, Robotics, Drones, Embedded Systems, and Mathematics**.

---

## Why This Skill?

Technical books often explain *what* something is without making it immediately clear:

* Why does this concept exist?
* What problem does it solve?
* How does the mathematics connect to the implementation?
* What is actually happening inside the code?
* What happens if a parameter changes?
* Why would we use this approach instead of another?
* How would I debug it when it fails?

Technical Book Tutor is designed to answer those questions systematically.

The objective is not memorization.

The objective is:

> **Understand → Derive → Implement → Debug → Apply → Retain**

---

## Features

### Simple Language, Technical Depth

Complex concepts are explained using:

```text
Simple intuition
       ↓
Technical concept
       ↓
Formal definition
       ↓
Formula / algorithm
       ↓
Worked example
       ↓
Code implementation
       ↓
Practical application
```

The language stays simple without removing the underlying technical depth.

---

### Mathematics-First When Necessary

When mathematics is important, the tutor provides:

1. The formula
2. Meaning of every symbol
3. Plain-English interpretation
4. Numerical substitution
5. Step-by-step calculation
6. Derivation when useful
7. Effect of changing variables
8. Connection to implementation

For example:

```text
Formula
   ↓
What does each symbol mean?
   ↓
Why does this formula exist?
   ↓
Put numbers into it
   ↓
Calculate it
   ↓
Understand what the result means
   ↓
See how it appears in code
```

---

### Code Explanation

When an excerpt contains code, the tutor explains:

* What problem the code solves
* The underlying algorithm
* The formula behind it when applicable
* Inputs and outputs
* Data types
* Tensor/array shapes
* Important lines
* Execution flow
* Expected behavior
* Common errors
* Debugging strategy
* Version-specific issues

The goal is not merely to understand what the code says.

The goal is to understand **why the code works**.

---

### Domain-Specific Teaching

The skill includes specialized references for:

| Domain           | Focus                                                |
| ---------------- | ---------------------------------------------------- |
| Mathematics      | Formulas, derivations, intuition, numerical examples |
| Programming      | Algorithms, APIs, memory, debugging                  |
| Machine Learning | Models, tensors, loss, gradients, optimization       |
| Computer Vision  | Images, convolution, filters, geometry               |
| CUDA             | Kernels, threads, blocks, memory, performance        |
| Robotics         | Sensors, estimation, control, coordinate frames      |
| Embedded Systems | MCU, peripherals, interrupts, RTOS, timing           |

---

## Repository Structure

```text
technical-book-tutor/
│
├── SKILL.md
│
├── references/
│   ├── mathematics.md
│   ├── programming.md
│   ├── machine_learning.md
│   ├── computer_vision.md
│   ├── cuda.md
│   ├── robotics.md
│   └── embedded_systems.md
│
└── examples/
    └── ideal_lesson.md
```

### `SKILL.md`

The main orchestration file.

It defines:

* teaching methodology
* lesson structure
* mathematics protocol
* programming protocol
* debugging protocol
* active-learning system
* visual explanation rules
* continuity between chapters
* quality checks

### `references/`

Domain-specific teaching instructions.

The tutor can use the appropriate reference depending on the subject being studied.

### `examples/`

Contains an example of what a high-quality lesson should look like.

---

# How It Works

Give the tutor a small section of a technical book.

For example:

```text
Here are the next 3 pages from Hands-On Machine Learning.

[Paste excerpt]

Teach me this using the Technical Book Tutor Skill.
```

The tutor will transform it into a structured lesson.

---

# Default Lesson Structure

A substantial lesson follows this structure:

```text
1. CRUX
       ↓
2. PREREQUISITES
       ↓
3. NEW CONCEPTS
       ↓
4. CONCEPT-BY-CONCEPT TEACHING
       ↓
5. HOW EVERYTHING CONNECTS
       ↓
6. DEBUGGING / FAILURE MODES
       ↓
7. PRACTICAL APPLICATION
       ↓
8. MINI CHALLENGE
       ↓
9. CHECK MY UNDERSTANDING
       ↓
10. KNOWLEDGE GRAPH
       ↓
11. WHAT COMES NEXT?
```

Sections are skipped when they are not relevant.

---

# Teaching Philosophy

## 1. Intuition Before Formalism

Instead of immediately starting with:

[
y = f(x)
]

the tutor first explains what the relationship means conceptually.

Then the mathematics is introduced.

---

## 2. Formula → Code

Whenever possible:

```text
Mathematical idea
       ↓
Algorithm
       ↓
Code
```

For example:

```text
Loss function
     ↓
Gradient
     ↓
Parameter update
     ↓
PyTorch / TensorFlow code
```

This makes mathematical ML concepts easier to connect to actual implementations.

---

## 3. Decompose Complex Problems

A difficult topic is broken down:

```text
Complex problem
      ↓
Subproblem 1
Subproblem 2
Subproblem 3
      ↓
Individual operations
      ↓
Complete system
```

This prevents complicated engineering concepts from becoming one large block of unexplained information.

---

## 4. Active Learning

The tutor does not simply provide answers.

It asks questions such as:

> What would happen if the stride were doubled?

> Why would we use this method instead of the alternative?

> What would break if this assumption were removed?

> How would you debug this implementation?

The learner must reason about the concept.

---

# Example Learning Flow

Suppose you are studying convolution.

The tutor might establish:

```text
Image
  ↓
Local image patch
  ↓
Kernel
  ↓
Element-wise multiplication
  ↓
Summation
  ↓
Output pixel
  ↓
Repeat
  ↓
Feature map
```

Then it provides the mathematical operation:

[
Y(i,j)=\sum_m\sum_n X(i+m,j+n)K(m,n)
]

Then it explains every symbol.

Then it performs a small numerical example.

Then it connects the concept to CNNs.

Then it gives a coding challenge.

This creates a complete conceptual chain:

```text
Intuition
    ↓
Math
    ↓
Algorithm
    ↓
Code
    ↓
CNN
    ↓
Real application
```

---

# Intended Use

This Skill works particularly well with books such as:

* Hands-On Machine Learning
* Hands-On Computer Vision
* Digital Image Processing
* CUDA programming books
* Robotics textbooks
* Embedded systems books
* Control systems textbooks
* Deep learning books
* Computer graphics books
* Computer architecture books
* C/C++ programming books
* Mathematics for ML books

---

# Recommended Workflow

Do not paste an entire book at once.

Use approximately:

```text
2–5 pages
   ↓
Learn
   ↓
Answer questions
   ↓
Solve challenge
   ↓
Continue
```

This allows the tutor to maintain a conceptual thread while keeping each lesson manageable.

---

# Example Prompt

After installing the Skill, use:

```text
I am studying this book.

Here are the next 3 pages:

[PASTE PAGES]

Teach me this excerpt using the Technical Book Tutor methodology.

Focus especially on:
- simple explanations,
- formulas,
- code,
- intuition,
- worked examples,
- connections to previous concepts,
- common mistakes,
- practical applications.

Do not merely summarize the pages.
```

---

# Design Principles

Technical Book Tutor follows several principles:

### Explain, Don't Paraphrase

The tutor should reconstruct the explanation rather than simply rewriting the author's paragraphs.

### Simple Doesn't Mean Shallow

Advanced mathematics and engineering concepts should remain technically accurate.

### Show the Formula

If mathematics is important, show it.

### Explain the Code

Code should not be presented without explaining its underlying logic.

### Connect Concepts

New knowledge should connect to existing knowledge.

### Practice Matters

Understanding is tested through reasoning and application.

### Debugging Is Part of Learning

A concept is not fully understood until the learner can reason about what happens when the implementation fails.

---

# Future Extensions

Possible future additions include:

* `signal_processing.md`
* `computer_graphics.md`
* `control_systems.md`
* `computer_architecture.md`
* `operating_systems.md`
* `networking.md`
* `robotics_control.md`
* `electronics.md`
* `statistics.md`
* `reinforcement_learning.md`
* `transformers.md`

The modular structure makes these extensions easy to add.

---

# License

Choose a license appropriate for your repository.

For a permissive open-source project, MIT is a simple option.

---

## Author

**Haseeb Khan Bettani**

Built as a modular AI-assisted learning system for mastering technical books through active understanding rather than passive summarization.
