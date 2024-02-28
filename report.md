# Report for assignment 4

## Project

Name: Bitfocus Companion

URL: [Bitfocus](https://github.com/bitfocus/companion), [Fork](https://github.com/dd2480-group14-2024/companion)

"Bitfocus Companion enables the reasonably priced Elgato Streamdeck to be a professional shotbox surface for a huge amount of different presentation switchers, video playback software and broadcast equipment."

## Onboarding experience

The project we worked on in assignment 3 did not have a very active community, a lot of tests failed and the documentation was very poor so we chose to go with another project this time around. The experience was completely different. Bitfocus Companion has a very active community of developers and users so it was more fun to work on. The documentation was well made and consisted of step-by-step guides on how to set up the developer environment for any platform, and there were also other useful documents available for developers such as information on how to contribute to the project.

## Effort spent

For each team member, how much time was spent in

1. plenary discussions/meetings;

2. discussions within parts of the group;

3. reading documentation;

4. configuration and setup;

5. analyzing code/output;

6. writing documentation;

7. writing code;

8. running code?

For setting up tools and libraries (step 4), enumerate all dependencies
you took care of and where you spent your time, if that time exceeds
30 minutes.

## Overview of issues and work done.

Title: Add "Duplicate Step" button #2584

URL: [#2584](https://github.com/bitfocus/companion/issues/2584)

Summary: The software includes a feature that allows users to associate a button with specific sequences of actions, which can be executed step by step. Occasionally, steps involve very similar action sequences. To address this, the feature incorporates a button that enables the duplication of a step, eliminating the need for users to redo work over and over.

Scope: The implementation required changes to five different source files. The change affects one component in the emulator software but code had to be written for the server as well to handle the socket communication.

## Requirements for the new feature or requirements affected by functionality being refactored

Optional (point 3): trace tests to requirements.

## Code changes

### Patch

(copy your changes or the add git command to show them)

git diff ...

Optional (point 4): the patch is clean.

Optional (point 5): considered for acceptance (passes all automated checks).

## Test results

Overall results with link to a copy or excerpt of the logs (before/after
refactoring).

## UML class diagram and its description

### Key changes/classes affected

Optional (point 1): Architectural overview.

Optional (point 2): relation to design pattern(s).

## Overall experience

What are your main take-aways from this project? What did you learn?

How did you grow as a team, using the Essence standard to evaluate yourself?

Optional (point 6): How would you put your work in context with best software engineering practice?

Optional (point 7): Is there something special you want to mention here?
