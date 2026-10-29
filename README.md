# Scientific Computing Lab — Team 5

MATLAB coursework for the **Scientific Computing Lab** at the **Technical University of Munich (TUM)**, winter semester **2026/2027**.

This repository contains Team 5's worksheet implementations and will be extended throughout the course. The current repository contains Worksheet 1; implementation and verification are ongoing.

## Course Overview

The course introduces numerical methods through programming exercises and applications. Topics include:

- Discrete systems and Markov chains.
- Explicit and implicit time-stepping methods for ordinary differential equations (ODEs).
- Numerical methods for stationary and time-dependent partial differential equations (PDEs).
- Solvers for large, sparse linear systems.
- Adaptivity and adaptive grid refinement.
- Applications in fluid dynamics and heat transfer.

The expected background includes basic linear algebra and differential calculus. MATLAB is the programming language used for the assignments.

## Worksheets and Schedule

| Worksheet | Topic | Submission deadline | Oral examination |
| --- | --- | --- | --- |
| 1 | Analyzing Discrete Processes | 15 Nov 2026, 23:59 | 17 Nov 2026 |
| 2 | Solving ODEs Explicitly | 6 Dec 2026, 23:59 | 8 Dec 2026 |
| 3 | Solving ODEs Implicitly | 3 Jan 2027, 23:59 | 5 Jan 2027 |
| 4 | Solving Stationary PDEs | 17 Jan 2027, 23:59 | 19 Jan 2027 |
| 5 | Solving Time-dependent PDEs | 31 Jan 2027, 23:59 | 2 Feb 2027 |

These dates come from the **provisional schedule in the course export dated 30 October 2026**. Check Moodle for changes, examination locations, and group time slots. Each group must register for an examination slot for every worksheet.

## Repository Structure

```text
SciComp-Lab-team5/
├── README.md
└── worksheet_1/
    ├── game.m             # Game entry point and GUI event handling
    ├── game.fig           # Provided graphical interface
    ├── mchoice.m          # Computer prediction policies and move selection
    └── gen_human_move.m   # Provided human-move generator for simulations
```

Further worksheet directories will be added as the course progresses. For Worksheets 2–5, the general submission guidelines request a main script named `worksheetX.m`, where `X` is the worksheet number, unless the worksheet specifies otherwise.

## Getting Started

### Requirements

- MATLAB with a graphical desktop for the Worksheet 1 interface.
- No additional toolboxes are required by the course assignments.

Submitted solutions must run in MATLAB. The course does not accept Octave solutions.

### Run Worksheet 1

Open the repository in MATLAB and set the repository root as the **Current Folder**. Then run:

```matlab
cd worksheet_1
game
```

Keep `game.m`, `game.fig`, `mchoice.m`, and `gen_human_move.m` in the same directory.

In the interface, select a prediction policy and a game mode, configure the applicable parameters, and start the game. The interface supports manual play and automatic simulations. Use **Save data** to export the recorded results and transition-matrix data to a `.mat` file.

The code is coursework in progress; launching the interface does not imply that every worksheet exercise has been completed or validated.

## Worksheet 1: Rock–Paper–Scissors

Worksheet 1 studies discrete state transitions using a rock–paper–scissors game. Moves are encoded as:

| Value | Move |
| --- | --- |
| `1` | Rock |
| `2` | Paper |
| `3` | Scissors |

The computer predicts the human player's next move and selects a move that beats that prediction. The worksheet covers three policies:

- **Policy 1:** Use the previous human move and the parameters `param_a` and `param_b` to generate a prediction with prescribed probabilities.
- **Policy 2:** Choose the most likely next human move from the estimated transition matrix.
- **Policy 3:** Sample a predicted human move from the probabilities in the estimated transition matrix.

For Policy 1, the parameters must satisfy `0 <= param_a <= param_b <= 1`. A MATLAB function that uses these global variables must declare them with `global param_a param_b` in its own workspace.

The worksheet tasks include implementing Policy 1, comparing the policies, investigating transition-matrix convergence, and extending the code to track and save the computer player's transition matrix.

The supplied worksheet permits changes to `game.m` and `mchoice.m`. It specifies that `game.fig` and `gen_human_move.m` should remain unchanged. An optional alternative human strategy may be implemented separately as `gen_human_move_mod.m`.

## Code Organization

The course recommends the following conventions for new code:

- Use `snake_case` for function names, `TitleCase` for class names, and `camelCase` for variables.
- Place larger or important functions in separate `.m` files.
- Keep the main script focused on running the experiment; place helper functions in separate files where appropriate.
- Prefer vector and matrix operations when suitable.
- Use descriptive names and document inputs, outputs, and relevant assumptions.
- Print all required numerical results and match the table orientation requested in the worksheet.
- Give plots informative titles, axis labels, and appropriate scales.

Follow worksheet-specific interfaces and restrictions when working with the supplied starter code. In particular, Worksheet 1 is an exception to the general main-script requirement. Worksheet 3 requires an independently implemented Newton method rather than a toolbox implementation.

## Submission

Before submitting a worksheet:

1. Run the solution in MATLAB and check that all required files are included.
2. Confirm that the required tables, numerical outputs, and plots can be reproduced.
3. Package the files in an archive, for example `ws1_group5.tar.gz` for Worksheet 1.
4. Upload the archive to the corresponding Moodle submission page before the deadline. One submission per group is sufficient; the latest submission before the deadline is used.
5. Complete the worksheet result tables and bring them to the oral examination, either digitally or in print. The worksheet PDFs do not need to be submitted.

Questions at the end of each worksheet are intended for oral-examination preparation. Written answers to those questions do not need to accompany the code submission.

## Assessment and Oral Examinations

Assessment combines a shared group score for the code with an individual score for the oral examination. Code and examination questions contribute equally. The five worksheets have relative weights of **1 : 2 : 2 : 2 : 2**.

All group members must attend the in-person examinations and be able to explain the submitted code, numerical methods, and results. Questions may extend beyond the preparation questions printed on the worksheet. Consult Moodle's oral examination rules for attendance and lateness requirements.

## Course References

This README summarizes the course materials exported on **30 October 2026**:

- *Contents of the course* and *Schedule (provisional)*.
- *Lecture 0 — Organizational Aspects*.
- *Recommendations for structuring your code*.
- *Submission Guidelines* and *Oral Exam Rules*.
- *Worksheet 1* and the worksheet submission-page descriptions.

Moodle is the authoritative source for current assignment instructions, deadlines, and examination arrangements.
