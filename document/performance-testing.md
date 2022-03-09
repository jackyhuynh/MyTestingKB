## Performance Testing
### A. Introduction:
- Performance testing is a testing technique, performed to determine the responsiveness and stability of 
a software system under various workload 
- Performance testing metrics are: scalability, reliability and resource usage
- Type:
  - Load Testing
  - Stress Testing
  - Soak Testing
  - Spike Testing
- Performance testing is a non-functional testing
- Retrieved from (18)

### B. Example/Explain:
#### Example 1 using Locustio
- we can perform performance testing using Python 
- locust package of Python can perform this task.
- locust is coding base package. Therefore, we can store as script and perform this with other testing technique
- install from bash
```bash
$ pip install locustio
```
- Boiler of performance testing script may look like:
```python
from locust import HttpLocust, TaskSet, task, between

class TestCases(TaskSet):
    def on_start(self):
        self.payload = {"email": "john@example.com", "password":123}
        self.login()

    def on_stop(self):
        self.logout()

    def login(self):
        self.client.post("/login", self.payload)

    def logout(self):
        self.client.post("/logout", self.payload)

    @task(2)
    def visit_count(self):
        self.client.get("/visit")

    @task(1)
    def profile(self):
        self.client.get("/profile")

class LocustUsers(HttpLocust):
    task_set = TestCases
    wait_time = between(5, 9)
```
- Run the script above from bash
```bash
locust -f mylocustfile.py -- host= https://template-blog.herokuapp.com/
```
- If the code has no issue then we will see something like this
```bash
[2022-02-10 10:13:16,324]                     /INFO/locust.main: Starting web monitor at http://*:8089
```
- Navigate to local host http://localhost:8089, there is will be a graphic interface appear
```diff
- Enter the number of total user to simulate: 10000
- Enter the Hatch Rate: 99
+ If you give the number of users to simulate as 10000 and Hatch rate as 99 then all 10000 users will be activated within 99 seconds 
```
#### Example 2 using datetime package:
- There are methods that using datatime, timeit, cProfile for performance testing but I may argue that it wont be efficient as the locustio package.
- May end up to manually do extra work compare to locustio

### C. Advantages/Disadvantage
#### Advantage:
- Verifies the speed, accuracy, and stability of the software match expectation.
- Assists the system by authenticating the responsiveness and managing the scalability and reliability of software features.
- Retrieved from (14)

#### Disadvantage:
- Can be a costly mistake if done haphazardly, leading to inaccurate results and conclusions.
- Carried out on multiple devices in different locations to check whether a user faces difficulties. Hence this testing can be costly.
- Retrieved from (14)

### D. Applications:
- Performance testing should be performed for any kind of applications since we all want to know how our application is performed. 
We can guarantee the software applications can handle and manage the workload efficiently
### E. Reference:
- [Write your first performance/load test in Python](https://medium.com/@kundan3034/write-your-first-performance-load-test-in-python-e8e2132ef775) (17)
- [Performance Testing](https://www.tutorialspoint.com/software_testing_dictionary/performance_testing.htm) (18)
<hr>