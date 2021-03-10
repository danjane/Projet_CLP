# Bibliographie

## The art of software testing. Myers et al
https://www.orellfuessli.ch/shop/home/artikeldetails/ID38725524.html?ProvID=10917737&gclid=EAIaIQobChMItr-1wZum7wIVE853Ch0DVgBsEAYYBSABEgJozfD_BwE

### Un exemple intéressant
p.7

Patient goes to the doctor feeling unwell. \
Doctor finds nothing wrong => SUCCESS \
Doctor diagnoses ulcer and begins healing process => FAIL

Waaat ?!

**"Testing is the process of executing a program with the intent of finding errors."**

Human testing methods: code inspection, walkthroughs, user testing (usability) \
"If you thought designing and coding that program was hard, you ain’t seen nothing yet."

Test case design techniques discussed in chapter 4 include:
* Logic coverage. \
Tests that exercise all decision point outcomes at least once, and ensure that all statements or entry points are executed at least once.
* Equivalence partitioning. \
Defines condition or error classes to help reduce the number of finite tests. Assumes that a test of a representative value within a class also tests all values or conditions within that class.
* Boundary value analysis. \
Tests each edge condition of an equivalence class; also considers output equivalence classes as well as input classes.

p.114
The SOFTWARE DEVELOPMENT PROCESS

End User -> Requirements -> Objectives -> External specification -> System design -> Program structure design -> Module interface specifications -> Code

* Requirements specify why the program is needed.
* Objectives specify what the program should do and how well the program should do it.
* External specifications define the exact representation of the program to users.
* Documentation associated with the subsequent processes specifies, in increasing levels of detail, how the program is constructed.





## Introduction to software testing. Ammann and Offutt.
https://www.orellfuessli.ch/shop/home/suggestartikel/ID46449130.html?sq=Introduction%20to%20Software%20Testing&stype=productName

p. 36

Introduction to Bezier's *Test Process Maturity Levels* 

* Level 0 \
There is no difference between testing and debugging.
* Level 1 \
The purpose of testing is to show correctness.
* Level 2 \
The purpose of testing is to show that the software does not work.
* Level 3 \
The purpose of testing is not to prove anything specific, but to
reduce the risk of using the software.
* Level 4 \
Testing is a mental discipline that helps all IT professionals
develop higher- quality software.

**Level 3 understanding of tests: "testing can show the presence, but not the absence, of failures."**

p.53 V-Model

"standard advice is to design the tests concurrently with each development activity, even though the
software will not be in an executable form until the implementation phase.
The reason for this advice is that the mere process of designing tests can identify defects in design 
decisions that otherwise appear reasonable."

p.53 Fig2.3 for V-model, maybe with Fig1.1 on costs?

p.69

Test automation : The use of software to control the execution of tests, the comparison of actual outcomes to predicted
outcomes, the setting up of test preconditions, and other test control and test reporting functions

DAD \
High cohesion low binding, 
Impact of OOP on testing



## Test driven development, by example. Kent.
https://www.orellfuessli.ch/shop/home/suggestartikel/ID3851358.html?sq=Test%20Driven%20Development.%20By%20Example&stype=productName

**to read**

## Fuzzing
Quite a cute method for automated testing. 

https://colab.research.google.com/github/damorimRG/practical_testing_book/blob/master/testgeneration/fuzzing.ipynb#scrollTo=8u4LSr0QkAN9

Q When libFuzzer is not a good solution for a problem?

If the test inputs are validated by the target library and the validator asserts/crashes on invalid inputs, in-process fuzzing is not applicable.
Bugs in the target library may accumulate without being detected. E.g. a memory corruption that goes undetected at first and then leads to a crash while testing another input. This is why it is highly recommended to run this in-process fuzzer with all sanitizers to detect most bugs on the spot.
It is harder to protect the in-process fuzzer from excessive memory consumption and infinite loops in the target library (still possible).
The target library should not have significant global state that is not reset between the runs.
Many interesting target libraries are not designed in a way that supports the in-process fuzzer interface (e.g. require a file path instead of a byte array).
If a single test run takes a considerable fraction of a second (or more) the speed benefit from the in-process fuzzer is negligible.
If the target library runs persistent threads (that outlive execution of one test) the fuzzing results will be unreliable.

I created a simple example in Colab with the function dan_double (and an obvious bug) to illustrate fuzzing with a light-hearted example:
https://colab.research.google.com/drive/1lc5SFhzgH3s5DagocQkaHzujQXtcV9Ad?usp=sharing




## Websites

https://softwaretestingboard.com/q2a/3379/what-is-software-testing#axzz6lPFtp4l3
The following are some of the types of Software Testing.

Unit testing
Integration testing
System testing
Sanity testing
Smoke testing
Interface testing
Regression testing
Beta/Acceptance testing
Performance Testing
Load testing
Stress testing
Volume testing
Security testing
Compatibility testing
Install testing
Recovery testing
Reliability testing
Usability testing
Compliance testing
Localization testing
Blackbox testing
Whitebox testing

https://www.academia.edu/13555351/Testing_Types_and_Testing_Paradigms
Test has what knowledge of architecture? (Firesmith "How: by Technique")
1. White Box Testing
2. Black Box Testing
3 Gray Box Testing

https://en.wikipedia.org/wiki/Software_testing#The_%22box%22_approach
1. White-box testing (also known as clear box testing, glass box testing, transparent box testing, and structural testing) verifies the internal structures or workings of a program, as opposed to the functionality exposed to the end-user.
2. Black-box testing (also known as functional testing) treats the software as a "black box," examining functionality without any knowledge of internal implementation, without seeing the source code. The testers are only aware of what the software is supposed to do, not how it does it.
3. Grey-box testing (American spelling: gray-box testing) involves having knowledge of internal data structures and algorithms for purposes of designing tests while executing those tests at the user, or black-box level. The tester will often have access to both "the source code and the executable binary." Grey-box testing may also include reverse engineering (using dynamic code analysis) to determine, for instance, boundary values or error messages.




