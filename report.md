# Report for assignment 4

## Project

Name: Bitfocus Companion

URL: [Bitfocus](https://github.com/bitfocus/companion), [Fork](https://github.com/dd2480-group14-2024/companion)

"Bitfocus Companion enables the reasonably priced Elgato Streamdeck to be a professional shotbox surface for a huge amount of different presentation switchers, video playback software and broadcast equipment."

## Onboarding experience

The project we worked on in assignment 3 did not have a very active community, a lot of tests failed and the documentation was very poor so we chose to go with another project this time around. The experience was completely different. Bitfocus Companion has a very active community of developers and users so it was more fun to work on. The documentation was well made and consisted of step-by-step guides on how to set up the developer environment for any platform, and there were also other useful documents available for developers such as information on how to contribute to the project.

## Effort spent

__Leo Vainio__

1. plenary discussions/meetings;

2. discussions within parts of the group;

3. reading documentation;

4. configuration and setup;

5. analyzing code/output;

6. writing documentation;

7. writing code;

8. running code?


__placeholder__

1. plenary discussions/meetings;

2. discussions within parts of the group;

3. reading documentation;

4. configuration and setup;

5. analyzing code/output;

6. writing documentation;

7. writing code;

8. running code?



## Overview of issues and work done.

Title: Add "Duplicate Step" button #2584

URL: [#2584](https://github.com/bitfocus/companion/issues/2584)

Summary: The software includes a feature that allows users to associate a button with specific sequences of actions, which can be executed step by step. Occasionally, steps involve very similar action sequences. To address this, the feature incorporates a button that enables the duplication of a step, eliminating the need for users to redo work over and over.

Scope: The implementation required changes to five different source files. The change affects one component in the emulator software but code had to be written for the server as well to handle the websocket communication.

## Requirements for the new feature or requirements affected by functionality being refactored

### #2584 Add duplicate step button

R1: User interface. 

A button for duplicating a step should be added to the edit button component in the web UI next to the already existing "add step" and "remove step" buttons. 

R2: Feature description.

Users should be able to duplicate a step when editing a button's functionality. When duplicating a step, a new step should be created for the button that contains a copy of the sequence of actions that exist in the current step. 

R3: Integration.

The feature should integrate seamlessly with the current software and should not cause any breaks somewhere else.

## Code changes

### Patch

#### #2584 Add duplicate step button

The link to the branch containing the patch as well as links to the changes in each affected file for this issue is presented below. The patch is clean (point 4) as it primarily introduces new code into the project without introducing any unnecessary alterations or additions to whitespace.

[#2584](https://github.com/dd2480-group14-2024/companion/tree/feature/issue-2584/add-duplicate-step-button), 
[EditButton.tsx](https://github.com/dd2480-group14-2024/companion/blob/feature/issue-2584/add-duplicate-step-button/webui/src/Buttons/EditButton.tsx#L437), 
[SocketIO.ts](https://github.com/dd2480-group14-2024/companion/blob/feature/issue-2584/add-duplicate-step-button/shared-lib/lib/SocketIO.ts#L172), 
[IControlFragments.js](https://github.com/dd2480-group14-2024/companion/blob/feature/issue-2584/add-duplicate-step-button/companion/lib/Controls/IControlFragments.js#L49), 
[Controller.js](https://github.com/dd2480-group14-2024/companion/blob/feature/issue-2584/add-duplicate-step-button/companion/lib/Controls/Controller.js#L657), 
[Normal.js](https://github.com/dd2480-group14-2024/companion/blob/feature/issue-2584/add-duplicate-step-button/companion/lib/Controls/ControlTypes/Button/Normal.js#L848)

Optional (point 4): the patch is clean.

Optional (point 5): considered for acceptance (passes all automated checks).

## Test results

### Before

![before img](./test_logs/log_before.png)

[Logs before](https://github.com/dd2480-group14-2024/assignment4/blob/main/test_logs/log_before.txt)

### After #2584

There were no specific tests for this issue before we started but one test was added (linked below) which is mostly linked to requirement R2. It checks that the duplicated step is a copy of the original one and not the same object. As seen in the logs below it is also clear that requirement R3 is fulfilled since the implementation causes no breaks in the other tests.

[Link to test]()

![After img](./test_logs/log_after_2584.png)

[Logs after](https://github.com/dd2480-group14-2024/assignment4/blob/main/test_logs/log_after_2584.txt)

## UML class diagram and its description

### Key changes/classes affected

#### #2584 UML diagram

The project uses the very popular model view controller (MVC) design pattern for their web UI interface. The diagram below contains the methods and fields in the classes that are affected by the patch for this issue and some other relevant ones. The client (EditButton class), which is part of the view (the web UI), sends a websocket emit event to the controller on the server side when a user presses a specific button in the UI. The handler calls the corresponding function in the ControlButtonNormal class which implements the ControlWithSteps interface. When the step has been added/duplicated the change is saved on the server, and the controller sends back the id of the new step to the client (EditButton). The ClientToBackendEventMap interface contains definitions for all the socket handler functions which the controller implements.

![Issue #2584](./assets/issue2584.drawio.png)

Optional (point 1): Architectural overview.

Optional (point 2): relation to design pattern(s).

## Overall experience

What are your main take-aways from this project? What did you learn?

How did you grow as a team, using the Essence standard to evaluate yourself?

Optional (point 6): How would you put your work in context with best software engineering practice?

Optional (point 7): Is there something special you want to mention here?
