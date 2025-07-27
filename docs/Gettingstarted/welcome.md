# Creating Custom AI Use Cases in SAP S/4HANA

## Context

In the rapidly evolving landscape of AI and machine learning, **Intelligent Scenario Lifecycle Management (ISLM)** has emerged as a critical framework that bridges the gap between data science endeavors and practical application development. ISLM plays a pivotal role in streamlining and optimizing the adoption of AI solutions, particularly within the SAP S/4HANA environment.

ISLM standardizes the integration and consumption of intelligent scenarios within SAP S/4HANA for both **Embedded** as well as **Side-by-Side** scenarios.

ISLM can be leveraged to perform lifecycle operations, including (scheduled) (re-)training and deployment as well as activation of the model that should be consumed by the business application, directly within SAP S/4HANA. MLOps in ISLM is supported in the context of ML use case (Intelligent Scenario).
<br>

## ISLM brief introduction

ISLM framework stacked into SAP S/4HANA, is the right tool for application developers for SAP S/4HANA. ISLM standardizes the integration and consumption of intelligent scenarios within SAP S/4HANA for both embedded as well as side-by-side scenarios. Thus, application developers are required to use ISLM to create, register, and publish new scenarios and to implement the consumption of that scenario within the business application.

ISLM can be leveraged to perform lifecycle operations, including (scheduled) (re-)training and deployment as well as activation of the model that should be consumed by the business application, directly within SAP S/4HANA. ML ops in ISLM is supported in the context of ML use case (Intelligent Scenario).

An application developer for SAP S/4HANA from SAP or customer/partner side, is mainly responsible for integrating the AI scenarios into the respective application. ISLM facilitates embedding AI into business application with a low code approach.

By the end of this workshop, participants will gain a comprehensive understanding of how ISLM empowers organizations to smoothly transition from data science experimentation to real-world AI application development, all within the SAP S/4HANA environment.

![](/docs/images/Overview.png)

- **Business User:** The end user who interacts with the business application and uses the predictions from machine learning for the business purpose.
- **Business Administrator:** A domain expert or analytics specialist, who can perform model trainings based on business context, evaluate model quality, and can activate a model for production usage.
- **Technical Administrator:** A system administrator who can perform the configurations of connectivity between different entities as well as maintains the technical configurations of the system.
- **ABAP Developer:** A developer who can create ABAP artifacts required for Intelligent Scenario registration.
- **Intelligent Scenario Owner:** A owner who creates, reviews and publishes Intelligent Scenario.
