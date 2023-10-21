# CS 131 Fall 2023 - Project Autograder

Hi there! This is a repo that contains an open-source subset of the autograder we'll be using for [CS 131 - Fall 2023](https://ucla-cs-131.github.io/fall-23-website/)'s course-long project: making an interpreter.

Using this repository / testing locally is **entirely optional**. It does not directly affect your grade. **You are free to only submit to Gradescope!**

This repository contains:

- the **full source code** for the autograder we deploy to Gradescope
- 20% of the test cases we evaluate your code on; these are the test cases that are public on Gradescope
    - each version of the project is in a `v*` folder;
    - the `tests` subdirectory contains source (`.br`) files for programs that should interpret and run without errors
    - the `fails` subdirectory contains source (`.br`) files for programs that should interpret successfully, but error

This repository does not contain:

- 80% of the test cases we evaluate your code on (until *after* the project is due)
- the plagiarism checker, which is closed-source
- the Docker configuration for the deployment; this is managed by Gradescope.
- canonical solutions for the past projects - those are in the [project template repo](https://github.com/UCLA-CS-131/fall-23-project-starter)

We'll note that with the current setup, we grant **five seconds for each test case to run**.

We've made a [separate repository for project template code](https://github.com/UCLA-CS-131/fall-23-project-starter).

## Usage

### Setup

This grader uses features of Python 3.11. So, **you must be running Python 3.11 locally**.

Next, clone this repository and make it your working directory:

```sh
$ git clone
# or, with SSH
$ git clone git@github.com:UCLA-CS-131/fall-23-autograder.git
...
cd fall-23-autograder
```

Now, you're ready to test locally.

### Testing Locally

To test locally, you will additionally need a **working implementation** of the project; the minimum example is an `interpreterv1.py`/`interpreterv2.py`/`interpreterv3.py` that implements the `Interpreter` class.

Place this in the same directory as `tester.py`. Then, to test project 1,

```sh
$ python3 tester.py 1
Running 5 tests...
Running v1/tests/test_add1.br...  PASSED
Running v1/tests/test_input1.br...  PASSED
Running v1/tests/test_print_multi.br...  PASSED
Running v1/fails/test_bad_var1.br...  PASSED
Running v1/fails/test_no_main.br...  PASSED
5/5 tests passed.
Total Score:    100.00%
```

The output of this command is **identical to what is visible on Gradescope pre-due date**, and they are the same cases that display on every submission. If there is a discrepancy, please let the teaching team know!

You may also specify a source file to the tester. This will run only the source file and not the rest of the tester. With this, you would manually specify input and would see the output in stdout.

```sh
$ python3 tester.py 1 v1/tests/test_add1.br
15
```

*Of course, you may specify any source file, not just ones we provide!*

Note: we also output the results of the terminal output to `results.json`.

## Bug Bounty

If you're a student and you've found a bug - please let the TAs know (confidentially)! If you're able to provide a minimum-reproducible example, we'll buy you a coffee - if not more!

## Licensing and Attribution

This code is distributed under the [MIT License](https://github.com/UCLA-CS-131/fall-23-autograder/blob/main/LICENSE).

Have you used this code? We'd love to hear from you! [Submit an issue](https://github.com/UCLA-CS-131/fall-23-autograder/issues) or send us an email ([bonnieliu@cs.ucla.edu](mailto:matt@bonnieliu@cs.ucla.edu)).
