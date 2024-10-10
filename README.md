# Software Testing

## Overview
This README provides insights into software testing methodologies, definitions of software quality, the stages of testing, common causes of software errors, and the software testing lifecycle (STLC). The content is aligned with the [SWEBOK V3.0: Guide to the Software Engineering Body of Knowledge](https://ieeecs-media.computer.org/media/education/swebok/swebok-v3.pdf).

## Introduction
Software testing ensures that the system meets both **functional** and **non-functional** requirements. The tester's role is to identify issues and improve the quality of the software.

### Software (IEEE Definition)
According to ISO 9000-3, software quality assurance includes:
- **Computer programs** (code)
- **Procedures**
- **Documentation**
- **Data** necessary for operating the software

### Software Quality (IEEE Definition)
Software quality refers to:
- The degree to which a system, component, or process meets specified requirements.
- The degree to which it satisfies customer or user needs.

### Software Quality (Pressman Definition)
Pressman defines software quality as:
- Conformance to functional and performance requirements.
- Adherence to development standards.
- Meeting implicit expectations for professionally developed software.

---

## The Software Development Process
A software process is a structured set of activities required to develop a software system. All processes typically involve:

1. **Specification**: Define what the system should do.
2. **Design and Implementation**: Define the organization of the system and implement it.
3. **Validation**: Ensure that the system fulfills customer requirements.
4. **Evolution**: Adapt the system to changing customer needs.

---

## Stages of Testing

1. **Component Testing**: Testing individual components such as functions or objects independently.
2. **System Testing**: Testing the system as a whole, particularly focusing on emergent properties.
3. **Customer Testing**: Testing with real client data to ensure the system meets client requirements.

---

## Software Testing Lifecycle (STLC)

1. **Requirements** → 2. **Design** → 3. **Development** → 4. **Testing** → 5. **Deployment** → 6. **Maintenance**

---

## Testing Methods

- **Model-based Testing**: Testing using models to represent the desired behavior of the system.
- **Manual Testing**: Following the developer's steps to identify potential issues.
- Considerations: Time, budget, and experience impact the effectiveness of testing.

### Software Testing Process Models

1. **Waterfall Model**
2. **Agile Model**
3. **Process Activities**: Validation with customers.

---

## Requirements Types

- **Functional Requirements**: Specify the services or features the system must offer.
- **Non-functional Requirements**: Describe system attributes such as performance, security, and scalability.

---

## Software Design

Design a software structure that includes:
- **Architecture Design**
- **Database Design**
- **Interface Design**
- **Component Selection and Design**

### Verification vs. Validation

- **Verification**: Ensures that the requirements are correct.
- **Validation**: Confirms that the system meets all the requirements.

---

## Software Quality Assurance (SQA)

- **Plan and implement** systematically.
- Integrated into all stages of the software development process.
- The goal of SQA is to minimize the cost of guaranteeing quality through activities performed throughout development.

---

## Defects and Errors

### Types of Defects

1. **Failure**: Deviation from expected behavior.
2. **Fault**: The underlying cause of a failure.
3. **Error**: Human action leading to a fault.

### Common Causes of Software Errors

1. **Faulty Requirements Definition**: Missing or incorrect requirements.
2. **Client-Developer Communication Failures**: Misunderstandings between clients and developers.
3. **Deliberate Deviations from Requirements**: Developers making unapproved changes.
4. **Logical Design Errors**: Incorrect formulas or decision logic.
5. **Coding Errors**: Syntax, logic, or runtime errors.
6. **Non-compliance with Documentation**: Failing to follow coding standards or templates.
7. **Shortcomings of Testing Process**: Incomplete or poorly executed test plans.
8. **User Interface Errors**: Poor user interface design or usability issues.
9. **Documentation Errors**: Mistakes in user manuals or online help.

---

## Software Development Lifecycle (SDLC)

Testing is an integral part of the SDLC, encompassing:
1. **Quality Assurance**: Ensures that the software is developed to high standards.
2. **Verification and Validation (V&V)**: Confirms that the product meets requirements and functions correctly.
3. **Error Types**: Understanding software errors, faults, and failures is crucial for reducing defects.

---

## Conclusion

This document provides an overview of software testing fundamentals, methods, and common pitfalls. With these guidelines, software quality can be assured through thorough testing and validation throughout the software lifecycle.