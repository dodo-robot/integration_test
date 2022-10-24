# Software Testing

Software testing is divided in two main branches: Functional Testing and Non-Functional Testing


Type of Testing | Functional Testing |  Non-Functional Testing 
--- | --- | ---  
Objective | Verify software actions | Verify software performance  
Area of Focus | User requirements | User expectation 
Ease of testing | black box testing | white box testing  
Functionality | what the product does | How the products works  
Execution | before non functional testing | right after functional testing  

## Functional testing steps

1. determine which functionality needs to be tested like main functionalities, error condition and messages
2. create input data as per the requirements specification
3. determine the output as per the requirements specification
4. execute prepared test cases
5. compare actual output from the execution with the expected result


# Functional testing types

1. unit tests
2. regression tests
3. integration tests
4. usability testing

# Unit testing

The idea is to atomically test each module of the application mocking out dependencies where needed
in order to achieve a good code coverage for ensuring to have tested the whole code base

# Regression testing

We want to test out all the modules after a new change has been made to enure that it didn't break anything

# Integration Testing

the idea is to test the interaction between multiple services in a production-like environment without mocking.
To do so we can leverage tools such docker and docker-compose to spin up all the components we need in a specific and predefined state in order to run tests.
The state of the componets can be set through initializing scripts.

# Usability Testing

it consists of emulating a real user interacting with the application. It can be done with tools such as Selenium which can simulate the interaction with the user interface

# Run unit test on local machine

To run integration test locally we need to spin up all the components and then run the tests

```bash
 python -m pytest ./tests/unit --no-header -vv
```

# Generate code coverage

```bash
python -m coverage run -m pytest .\tests\unit\ --no-header -vv
```

# Generate code coverage HTML report
```bash
coverage html
```

# Run integration test with docker compose

These tests can be executed from within a docker as well so to be easily integrated in an automated pipeline.


```bash
docker-compose up --build --abort-on-container-exit
```

# Tear down environment

```bash
docker-compose down
```


# Non Functional Testing

These tests evaluate the overall performance of the system and wheather there are bottleneks or other type of issues concerning scalability and availability. 
We refer to these tests as Performance Tests which can be divided in: 
1. <b>load testing</b>: checks the application’s ability to perform under anticipated user loads. The objective is to identify performance bottlenecks before the software application goes live.
2. <b>stress testing</b>: involves testing an application under extreme workloads to see how it handles high traffic or data processing. The objective is to identify the breaking point of an application.
3. <b>spike testing</b>:tests the software’s reaction to sudden large spikes in the load generated by users.
4. <b>endurance testing</b>: is done to make sure the software can handle the expected load over a long period of time.
5. <b>volume testing</b>: Under Volume Testing large no. of. Data is populated in a database, and the overall software system’s behavior is monitored. The objective is to check software application’s performance under varying database volumes.
6. <b>scalability testing</b>:  The objective of scalability testing is to determine the software application’s effectiveness in “scaling up” to support an increase in user load. It helps plan capacity addition to your software system.


Usually these tests needs to be run against a running application in a real infrastructure settings which means that a monitoring system should be in place in order to correlate data gathered from the performance test tool and the infrastructure logging system

# Useful links

[VIDEO - Functional Testing](https://www.youtube.com/watch?v=IGnZHgjU42Y)

[VIDEO - ci/cd integration testing with docker compose](https://www.youtube.com/watch?v=sWRC2HIQ3T8)


[locust.io experiments](https://medium.com/locust-io-experiments)
