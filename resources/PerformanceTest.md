# Performance Testing

## Abstract
This document introduces the concept of performance testing and outlines an approach using the `locustio` framework. A case study demonstrates how to perform performance testing on a blog website.

## Index Terms
Software performance testing, performance testing methodologies, software testing.

---

## 1. Introduction

### a. Performance Testing Definition
Performance testing is a non-functional testing technique used to evaluate the responsiveness, stability, and scalability of a software system under varying workloads. Key performance metrics include:
- **Scalability**
- **Reliability**
- **Resource usage**

There are four primary types of performance testing:
1. **Load Testing**
2. **Stress Testing**
3. **Soak Testing**
4. **Spike Testing**

### b. System Performance Degradation
According to [1], system performance degradation, especially in terms of handling required throughput, is a critical issue in many large industrial projects. Even after extensive functional testing, the system may still lack proper performance assessments [1].

An architecture review at AT&T revealed that **performance issues** are one of the three major fault categories in software development. Common problems include:
- Lack of performance estimates
- Absence of data collection plans
- Failure to allocate a performance budget

Insufficient performance planning often leads to deployment issues, impacting user satisfaction.

### c. Uneven Distribution of Resource Usage
A **Pareto-type distribution** often indicates an uneven distribution of resource usage across the system, requiring careful resource management.

---

## 2. Case Study: Performance Testing with `locustio`

### Example 1: Using `locustio`
Locust is a Python-based performance testing tool that allows you to write performance tests as scripts. It can be installed using:

```bash
pip install locustio
```

#### Sample Script
Below is a boilerplate script for performance testing with `locustio`:

```python
from locust import HttpLocust, TaskSet, task, between

class TestCases(TaskSet):
    def on_start(self):
        self.payload = {"email": "john@example.com", "password": 123}
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

#### Running the Test
To execute the performance test, run the following command in your terminal:

```bash
locust -f mylocustfile.py --host=https://template-blog.herokuapp.com/
```

Upon successful execution, you will see an output like:

```bash
[2022-02-10 10:13:16,324] /INFO/locust.main: Starting web monitor at http://*:8089
```

Open a browser and navigate to `http://localhost:8089`. You will be presented with a graphical interface where you can specify:
- Number of users to simulate (e.g., 10,000)
- Hatch rate (e.g., 99 users per second)

### Example 2: Alternatives (datetime, timeit, cProfile)
While Python’s `datetime`, `timeit`, and `cProfile` modules can also be used for performance testing, they typically require more manual effort compared to `locustio`, making `locustio` a more efficient option.

---

## 3. Advantages and Disadvantages

### Advantages
- **Verifies speed, accuracy, and stability**: Ensures the system meets performance expectations.
- **Improves responsiveness and scalability**: Helps to validate the reliability of the software under stress.
- **Enhances user satisfaction**: A properly tested system is less likely to experience performance bottlenecks.

### Disadvantages
- **Costly if done incorrectly**: Poor execution of performance tests can lead to inaccurate results.
- **Expensive for distributed testing**: Running tests across multiple devices and locations can be resource-intensive.

---

## 4. Applications
Performance testing is essential for any software application to guarantee that it can handle and manage workload efficiently. Whether testing a web application, mobile app, or large-scale enterprise system, performance testing helps to ensure smooth user experiences and system stability.

---

## 5. References

1. E. J. Weyuker and F. I. Vokolos, "Experience with performance testing of software systems: issues, an approach, and case study," IEEE Transactions on Software Engineering, vol. 26, no. 12, pp. 1147-1156, Dec. 2000. doi: [10.1109/32.888628](https://doi.org/10.1109/32.888628).
   
2. Kumar, K. "Write your first performance/load test in Python," Medium. Retrieved from [Medium Article](https://medium.com/@kundan3034/write-your-first-performance-load-test-in-python-e8e2132ef775).

3. Tutorial Points (n.d.), "Performance Testing." Retrieved from [Tutorials Point](https://www.tutorialspoint.com/software_testing_dictionary/performance_testing.htm).