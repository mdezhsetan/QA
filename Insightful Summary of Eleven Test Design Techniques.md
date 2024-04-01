This article gathered and summarized valuable information on eleven test design techniques as highlighted on [TMAP's website](https://www.tmap.net/building-blocks/test-design-techniques "TMAP's Test Design Techniques"). I've distilled this knowledge in hopes that it proves as beneficial to you as it has to me. Here are the details laid out comprehensively:

## How Do You Choose a Test Design Technique?

The appropriateness of a test design technique largely depends on the specific quality attributes or aspects of the system you wish to test. These aspects, or quality attributes, include: `functionality`, `detailed functionality`, `overarching functionality`, and `adaptability/usability/connectivity/performance`.

## Test Design Techniques

### 1. Functionality

Techniques focused on system input and processing:

#### 1.1 Semantic Test (SEM)

- **Description**: Validates correct system processing of meaningful input data according to specified business logic.

> **Example**: 
> Consider an online book store system that offers discounts based on membership levels (e.g., Silver, Gold, Platinum) and the type of books purchased (e.g., Fiction, Non-Fiction, Educational). SEM would involve creating test cases to verify that the system applies the correct discount percentage. For instance, a Platinum member purchasing Educational books might receive a 20% discount, whereas a Silver member buying Fiction books receives only a 5% discount. The test ensures the system accurately interprets both the membership level and the book category to apply discounts correctly.

#### 1.2 Syntactic Test (SYN)

- **Description**: Assesses system resilience against invalid or unexpected data formats.

> **Example**: 
> Testing an email field involves inputting various email formats to verify that the system accepts valid emails (e.g., `user@example.com`) and rejects invalid ones (e.g., `user@`, `@example.com`, or `user@example`).

### 2. Detailed Functionality

Techniques examining specific system functionalities in depth:

#### 2.1 Decision Table Test (DTT)

- **Overview**: Utilizes decision tables to validate complex decision-making logic and business rules.
>**Example**: 
   Imagine an online application for a university that offers different scholarship amounts based on a combination of criteria: GPA (Grade Point Average), extracurricular activities, and residency status. A decision table for this scenario would list conditions down the left side (e.g., GPA ranges, number of extracurricular activities, in-state or out-of-state residency) and possible actions (scholarship amounts) across the top. 
  > 
   For example, a student with a GPA of 3.8, participating in 3 extracurricular activities, and residing in-state might be eligible for a $5,000 scholarship. In contrast, an out-of-state student with a GPA of 3.5 and 2 extracurricular activities might qualify for a $3,000 scholarship. The decision table helps ensure the application systematically evaluates all combinations of conditions to award scholarships accurately, reflecting the university's policies. This methodical approach guarantees that no eligible student is overlooked and that the scholarship allocation process is both fair and transparent.

#### 2.2 Data Combination Test (DCT)

- **Overview**: Evaluates interactions between various sets of data inputs and their combined effects on system functionality.
>**Example**:
>Consider a smart home system that controls heating, lighting, and security based on user preferences, weather conditions, and time of day. The Data Combination Test would examine how the system responds to a wide array of input combinations to ensure optimal operation under various scenarios.
  >   
  For instance, on a cold winter evening (input set 1: low outside temperature), when the homeowner is away (input set 2: security mode is activated), the system should reduce indoor heating to save energy but keep security lights on for safety. Another test case might involve a sunny summer morning (input set 1: high outside temperature) with the homeowner present (input set 2: normal mode), where the system optimizes for comfort by adjusting indoor cooling while turning off unnecessary lights to save energy.
  >   
  Through DCT, the smart home system is rigorously tested to ensure it intelligently combines data from multiple sources (weather conditions, homeowner presence, and time of day) to automate the home's environment efficiently, providing both comfort and energy savings. This comprehensive testing approach helps identify any scenarios where the system's response might not align with expected outcomes, ensuring reliability and user satisfaction.

#### 2.3 Elementary Comparison Test (EVT)

- **Overview**: Conducts a detailed examination of system's decision points and functionalities at the most granular level.
  
> **Example**:
> Imagine a mobile app for a coffee shop that includes a loyalty points system. Customers earn points based on the dollar amount they spend, with a bonus multiplier for purchases over $20. The basic rule is: for every dollar spent, the customer earns 1 point; however, for purchases over $20, they earn 2 points for every dollar spent on the portion of their purchase above $20.
> The EVT would specifically test the system's logic in applying these point rules under various purchase amounts. Critical scenarios to evaluate might include:
> 
> - **Below the Bonus Threshold**: A purchase of $15 should result in 15 loyalty points being awarded. This scenario checks that the system correctly applies the base point rule without activating the bonus multiplier.
> - **Exactly at the Bonus Threshold**: A $20 purchase, testing whether the system correctly sticks to the base rule without prematurely activating the bonus multiplier.
> - **Just Above the Bonus Threshold**: A purchase of $21 tests the system's transition from the base rule to including the bonus multiplier for the amount above $20. In this case, the customer should receive 22 points - 20 points for the first $20, plus 2 points for the $1 above the threshold.

### 3. Overarching Functionality

Broad techniques assessing system-wide integration and data flow:

#### 3.1 Data Cycle Test (GCT)

- **Overview**: Focuses on identifying integration errors by tracking data flow across system components.

>**Example:** 
  Imagine a complex healthcare application designed to manage patient records across multiple departments within a hospital. The application integrates data from the emergency room, outpatient clinics, surgery, pharmacy, and billing departments. Each patient's journey through the hospital generates a significant amount of data, including initial assessments, diagnostic test orders and results, medication orders, procedural records, and billing information.
  >
  The GCT would simulate a patient's entire treatment cycle to ensure seamless data flow and integrity across all modules. For instance, a test scenario might follow a patient from an emergency admission due to a heart attack, through diagnostic tests like ECGs and MRIs, surgery (angioplasty), post-op care, medication orders, to final discharge and billing.
  > 
 Key points of verification might include:
 > 
  >  - Ensuring diagnostic test orders in the ER automatically appear in the radiology module for execution and that results are promptly reported back to the ER and cardiology.
  >  - Verifying that surgery schedules are updated in real time across relevant departments and that post-op medication orders are accurately relayed to the pharmacy.
  >  - Checking that all services rendered, from diagnostic tests to surgical procedures, are correctly captured by the billing system.

#### 3.2 Data Combination Test (DCT) - Broad Application

- **Overview**: Applies to testing combinations of inputs across the entire system for evaluating overarching functionality.


>**Example:** 
>Consider an online travel agency's platform that bundles flights, hotels, and car rentals. The DCT at a broader level would assess how the system manages and combines these various services based on user selections, promotional offers, and availability. For instance, a scenario might involve a customer booking a flight to Paris, adding a five-night stay at a boutique hotel, and renting a car. The test verifies the system's ability to accurately combine these services, apply any relevant discounts (e.g., a 10% off on car rentals with hotel booking), and present the final package price, ensuring seamless operation and accurate pricing across the platform.

### 4. Adaptability, Usability, Connectivity, Performance

Techniques for testing system operation under real-world conditions:

#### 4.1 Use Case Test (UCT)

- **Overview**: Tests system functionalities through use cases that describe sequences of actions yielding a valuable outcome.

> **Example**: 
> For an online booking system, UCT involves simulating a user's journey from searching for flights, selecting a flight, entering passenger details, making a payment, to receiving a booking confirmation. This tests the system's end-to-end functionality and user experience.

#### 4.2 Real Life Test (RLT)

- **Overview**: Simulates real-world conditions to assess system's performance, usability, and connectivity.

> **Example**: An e-commerce website launches a mobile app to increase accessibility. The RLT simulates diverse real-world conditions, such as low-bandwidth environments, high traffic periods, and usage on a wide range of devices with different screen sizes and operating systems. The objective is to ensure that the app maintains functionality, loads efficiently, and provides a consistent user experience across all conditions.

#### 4.3 Process Cycle Test (PCT)

- **Overview**: Checks the end-to-end cycle of processes within the system, focusing on workflow integration and management.

> **Example:**
> Consider a comprehensive software system designed for managing large-scale construction projects, which integrates project planning, resource allocation, progress tracking, and financial management. The PCT focuses on the seamless workflow from project inception through to completion, highlighting the system's capability to manage and synchronize various project elements across its lifecycle.
>
> A test scenario might begin with the initiation of a new project, where the system is tasked with allocating initial resources based on the project's scope and estimated budget. As the project progresses, the system must dynamically adjust resource allocations in response to real-time progress updates, such as delays due to weather or accelerated timelines owing to increased workforce productivity. The test would also include monitoring the system's financial management features, ensuring that cost tracking and budget adjustments are accurately reflected and reported in real-time.
>
> For example, if a particular construction phase is completed ahead of schedule, the system should automatically recalibrate resource allocation for subsequent phases, potentially freeing up resources or budget for other tasks. Conversely, if a delay occurs, the system must promptly notify project managers, suggest adjustments to the schedule, and provide an updated financial forecast.

### 5. Ensuring Data Integrity and Handling

#### 5.1 Data Cycle Test (GCT) & Syntactic Test (SYN)

- **Overview**: These tests verify data integrity and proper handling of both valid and invalid input formats throughout the system's lifecycle.

>**Example**: 
>Imagine an advanced data analytics platform designed to ingest, process, and analyze vast amounts of data from social media, news outlets, and financial reports to predict stock market trends. The GCT aspect would focus on ensuring that data flows seamlessly through the ingestion, processing, and analysis stages without loss or corruption. This includes verifying that data collected from various sources is accurately merged, cleansed, and prepared for analysis according to predefined rules.
>
>Alongside, the SYN aspect tests the system's ability to handle and validate the diverse formats of incoming data. For instance, ensuring that social media posts, which may contain emojis or hashtags, are correctly interpreted and that financial reports in PDF format are accurately converted into structured data. A specific test case might involve a syntactic validation where the system encounters an unusually formatted date in a financial report (e.g., "31st June 2024", an invalid date) and must either correct the error based on context or flag it for manual review.


This guide is designed to help software testers select and apply the most appropriate test design techniques based on the specific requirements and characteristics of their projects.
