# RSE 102: git-workflows-exercises

This repository contains the exercises for the topic _git workflows_ of the [RSE102](https://github.com/RSE-102/Lecture-Material) course.
The corresponding lecture slides can be found at [sustainable-simulation-software.gitlab.io](https://sustainable-simulation-software.gitlab.io/course-material/slides/git_intro/workflows/index.html#/title-slide).

The exercises should be worked on in groups of two people.
Start with forking this repository (each one of you), and decide which of the two
forks should act as the "main repository". Note that the exercises
build upon each other, so you need, for instance, exercise 1 to be completed before
you can continue with exercise 2. Each exercise is described in the comments at the top of the respective `.py` file.

Typically, each one of you will have to make one of the already existing tests pass. 
The tests in a file can be run with `pytest`, for instance, with `python3 -m pytest FILENAME.py`.
To run only the test you are working on, use `python3 -m pytest FILE.py -k TESTNAME`.


## Exercise 1

- distribute the two tasks and work on them in parallel:
  - create a branch for your task, giving it an appropriate name
  - commit the solution to your task in a single commit with appropriate name
  - push your commit to the remote repository
  - open a merge request into the main branch
- Together, integrate both tasks via merge requests, while taking care that the final git history is either semi-linear:
  ```sh
    * merge task B
    | \
    |  * task B
    | /
    * merge task A
    | \
    |  * task A
    | /
    * commit from which you start your work
    ```
  or linear:
  ```sh
    * task B
    |
    * task A
    |
    * comit from which you start your work
  ```



## Exercise 2

- repeat the same procedure as from exercise 1, but this time using the file `exercise2.py`
- this time we want a semi-linear history, which should now continue like this:
  ```sh
    * merge ex2 task B
    | \
    |  * ex2 task B
    | /
    * merge ex2 task A
    | \
    |  * ex2 task A
    | /
    * last commit of exercise 1
    ...
    ```
- again, proper commit messages and branch names should be used


## Exercise 3

- repeat the procedure from the previous exercises, but this time using the file `exercise3.py`
- we again want a semi-linear history, but this time the entire exercise should be done in one merge request:
  ```sh
    * merge ex3
    | \
    |  * ex3 task B
    |  * ex3 task A
    | /
    * merge ex2 task B (from last exercise)
    | \
    ...
    ```
- again, proper commit messages and branch names should be used


## Exercise 4

- in this exercise, we want to achieve yet a different layout of the git history:
  ```sh
    * merge ex4
    | \
    |  * merge ex4 task B
    |  | \
    |  |  * ex4 task B
    |  | /
    |  * merge ex4 task A
    |  | \
    |  |  * ex 4 task A
    |  | /
    |  * ex 4 task 0
    | /
    * merge ex3 (from last exercise)
    | \
    ...
    ```
   
   ## License
   
   See `License` file.
