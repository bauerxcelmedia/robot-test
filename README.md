# The Robot Test

Using Node.js, design and code up a Toy Robot Simulator. You may use another programming language, but please explain reasons why you choose to. Host your code in your Github account and send in your repo URL for review. You should expect to spend a decent amount of time (3-4 hours) on the exercise.

## Assessment Criteria

We're learning about you through the test, so put your best foot forward.  Essentially, you should be painting a picture of yourself through your code and solution design.  Show us how you would approach a typical project. Include a README file to document and provide instructions if necessary. If you have any questions regarding the details of this test, feel free to continue and record your assumptions in the README file.

- We want to see clean design and _sounds software engineering practices_.
- When setting up the repo, structure it such that it will be used as a working repo in the future.
- You should aim to deliver _production-ready_ code _with tests_.

## Description

The application is a simulation of a toy robot moving on a square tabletop, of dimensions 5 units x 5 units. There are no other obstructions on the table surface.

The robot is free to roam around the surface of the table, but must be prevented from falling to destruction. Any movement that would result in the robot falling from the table must be prevented, however further valid movement commands must still be allowed.

Create an application that can read in commands in the following format:

- PLACE X,Y,F
- MOVE
- LEFT
- RIGHT
- REPORT

PLACE will put the toy robot on the table in position X,Y and facing NORTH, SOUTH, EAST or WEST. The origin (0,0) can be considered to be the SOUTH WEST most corner.

The first valid command to the robot is a PLACE command, after that, any sequence of commands may be issued, in any order, including another PLACE command. 

The application should discard all commands in the sequence until a valid PLACE command has been executed.

- MOVE will move the toy robot one unit forward in the direction it is currently facing.
- LEFT and RIGHT will rotate the robot 90 degrees in the specified direction without changing the position of the robot.
- REPORT will announce the X,Y and F of the robot. This can be in any form, but standard output is sufficient.

A robot that is not on the table can choose the ignore the MOVE, LEFT, RIGHT and REPORT commands.

Input can be from a file, or from standard input, as the developer chooses.

Provide test data to exercise the application.

## Constraints

The toy robot must not fall off the table during movement. This also includes the initial placement of the toy robot.
Any move that would cause the robot to fall must be ignored.

## Examples

### Example 1)

Input:
```
PLACE 0,0,NORTH
MOVE
REPORT
```

Output: `0,1,NORTH`

### Example 2)

Input:
```
PLACE 0,0,NORTH
LEFT
REPORT
```

Output: `0,0,WEST`

### Example 3)

Input:
```
PLACE 1,2,EAST
MOVE
MOVE
LEFT
MOVE
REPORT
```
Output: `3,3,NORTH`
