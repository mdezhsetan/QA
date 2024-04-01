I have gathered and summarized information on eleven test design techniques as mentioned on the [TMAP's website.](https://www.tmap.net/building-blocks/test-design-techniques "https://www.tmap.net/building-blocks/test-design-techniques") I hope this knowledge could be beneficial for you, just as it was for me. Here you can find the details:

# **How do you choose a test design technique?**

Which technique is most appropriate depends on what exactly you want to test. Following you can see a number of test forms. These test forms, also called quality attributes, are examples of what you can test with a certain system:

>A. Functionality
  B. Detail functionality
  C. Overarching functionality
  D. Adaptability, usability, connectivity, performance, or usability

The last form of testing contains a number of elements. That's because most test design techniques that fall under it test multiple things at once.

To give you a clear picture, below we will categorize the eleven design techniques according to the test forms. Under each test form, you'll see which test design techniques can be used.

# **A. Functionality**

The two test design techniques that fall under "Functionality" have to do with input to a system.

## 1. **Semantic Test (SEM)**

This is a testing technique that focuses on the input data and its meaning within the context of the system. It verifies the system's ability to correctly process valid input data according to the defined business logic and use cases. Semantic testing ensures that when input data is provided to the system, it interprets the data correctly and performs the intended operations. 

`For instance, in a payroll system, semantic testing would check if the system correctly calculates pay based on hours worked and the correct pay rate.`

## 2. **Syntactic Test (SYN)**

Syntactic testing, on the other hand, is concerned with the system's ability to handle input data from a structural perspective. It assesses the system's resilience to invalid or unexpected data formats and values. This kind of testing ensures that the system can validate input data against the expected format, types, and ranges, and that it can handle errors without crashing or behaving unpredictably. It's essentially a test of the system's input validation mechanisms. 

`For example, syntactic tests would check if an email field rejects inputs without an '@' symbol or if a date field rejects formats that are not recognized as valid dates.`

# **B. Detail functionality**

The name of the test form says it all: design techniques that fall under this focus on a specific functionality.

## 3- **Decision Table Test (BTT)**

The Decision Table Test, also known as Business Test or Table Test, is a structured testing technique where complex business rules and decision logic that can be tabulated are validated. It involves creating a table, often called a decision table, which captures different combinations of input conditions and their corresponding expected actions or outputs. This technique is particularly useful for systems where the logic involves multiple input combinations that could lead to different outcomes. By systematically addressing all possible conditions, a decision table ensures that no scenario is left untested.

## 4- **Data Combination Test (DCT)**!

The Data Combination Test focuses on evaluating the interactions between different sets of data inputs and their combined effect on the system's functionality. This technique is used when the correct behavior of a system depends not just on individual input values, but on the combination of several inputs. It is akin to combinatorial testing where all possible permutations of input combinations are tested to ensure that the system handles data interdependencies correctly. The goal is to cover a wide range of scenarios with as few tests as possible, efficiently identifying any defects related to data processing logic.

## 5- **Elementary Comparison Test (EVT)**

The Elementary Comparison Test is a detailed examination of the system's decision points and individual functionalities. It breaks down the system processes into their most fundamental elements and examines the logic behind each decision point or comparison operation within the system. This test is aimed at verifying the smallest testable units in an application to identify any discrepancies at the most granular level. By focusing on the elementary operations, testers can isolate and identify the root cause of failures in the system's logic.

>***Example:***
>
>**===Scenario:===**  
>Imagine a simple online shopping cart system where a user can apply a discount code to their purchase. The discount should only apply if the user's total purchase amount is above $100.  
>
>**Elementary Comparison Operation:**  
>The elementary comparison in this scenario is the check that the system performs to determine whether the user's total purchase amount is greater than $100, which can be represented as:
>
>`if (totalPurchaseAmount > 100) {    applyDiscount();} else {    doNotApplyDiscount();}`
>
>The EVT would involve creating tests that verify this specific comparison operation under various conditions.
>
>**===Test Case 1=== - Exact Boundary Condition:**
>
>- Input: `**totalPurchaseAmount = 100**`
>- Expected Outcome: `**doNotApplyDiscount()**` operation is executed, no discount applied.
>
>**===Test Case 2=== - Just Above Boundary Condition:**
>
>- Input: `**totalPurchaseAmount = 100.01**`
>- Expected Outcome: `**applyDiscount()**` operation is executed, discount is applied.
>
>**===Test Case 3=== - Well Above Boundary Condition:**
>
>- Input: `**totalPurchaseAmount = 150**`
>- Expected Outcome: `**applyDiscount()**` operation is executed, discount is applied.
>
>**===Test Case 4=== - Below Boundary Condition:**
>
>- Input: `**totalPurchaseAmount = 99.99**`
>- Expected Outcome: `**doNotApplyDiscount()**` operation is executed, no discount applied.
>
>**===Test Case 5=== - Zero Boundary Condition:**
>
>- Input: `**totalPurchaseAmount = 0**`
>- Expected Outcome: `**doNotApplyDiscount()**` operation is executed, no discount applied.
>
>**===Test Case 6=== - Negative Boundary Condition:**
>
>- Input: `**totalPurchaseAmount = -50**`
>- Expected Outcome: `**doNotApplyDiscount()**` operation is executed, no discount applied and potentially an error is flagged for negative total.
>
>By testing these cases, the EVT would confirm that the system correctly compares the `**totalPurchaseAmount**` against the $100 threshold and applies the discount rule accurately in each scenario. This ensures that the comparison logic in the code functions correctly for the range of possible inputs it might encounter.


# **C. Overarching functionality**

Overarching functionality testing means looking at the whole. Many techniques examine specific components of a system. Test design techniques that focus on the overarching functionality can bring out errors that cannot be seen by specific tests.

## 6- **Data Cycle Testing (GCT)**

Data Cycle Testing, or Global Cycle Testing (GCT), is a testing method that aims to identify integration errors by focusing on the interactions and data flow between various components within a system. This technique tests how data is processed and passed through different modules or services in a cycle, ensuring that all parts of the system are seamlessly integrated and that data maintains its integrity throughout the entire processing cycle. It's particularly useful for detecting issues where data might be corrupted, lost, or incorrectly handled as it moves across system boundaries or between processes. 

>An example of GCT could be tracking a user's data as it moves through an e-commerce platform's services, from account creation, through browsing, cart management, checkout, and order fulfillment.`

## 7- **Data Combination Test (DCT)**

While previously mentioned in the context of specific functionality, the Data Combination Test can also be applied to overarching functionality. When used at a higher level, DCT involves testing combinations of inputs across the entire system to evaluate the system’s behavior under a wide range of scenarios. This form of DCT aims to ensure that when various system functions and modules interact, they do so correctly, regardless of the complexity of the input data they're handling. In this broader context, DCT would look at how different system modules process and respond to diverse data combinations, verifying that the overall functionality of the system is robust against a wide range of data scenarios. 

>For example, testing how a CRM system handles different combinations of customer data entries, updates, and retrieval processes across all its functionalities.`

# **IV. Compatibility, usability, connectivity, performance or usability**

There are several test design techniques that test one or more of the above terms.

## 8- **Use Case Test (UCT).**

Use Case Testing is a technique that identifies and tests a system's functionality by using "use cases," which describe a sequence of actions, typically performed by an actor (user or another system), that yield a valuable result for a particular stakeholder. It helps in identifying missing functionalities by bridging the gap between system design and actual user requirements.

> **Example**: In an e-commerce web application, a use case might be "Purchasing an item." The UCT would test the complete flow, from selecting an item and adding it to the cart, to entering shipping information, choosing a payment method, and completing the purchase. The test ensures that each step behaves as expected and that the user receives confirmation of the successful transaction.

## 9- **Real Life Test (RLT)**

Real Life Testing involves assessing the system’s performance, usability, and connectivity by simulating real-world conditions and usage. It evaluates how well the system integrates and interacts with other systems and how it performs under typical user operations.

> **Example**:For a web-based travel booking application, RLT would simulate users searching for flights, filtering results, booking a flight, and receiving a booking confirmation. The test would evaluate performance under heavy traffic, ease of navigation, and responsiveness of the application on different devices and browsers.

## 10- **Process Cycle Test (PCT)**

The Process Cycle Test checks the complete cycle of processes within a system, especially focusing on the integration of administrative and operational aspects. It ensures that workflows are correctly managed from start to finish and that the administration of these processes within an automated system works seamlessly.

> **Example**: In a web-based project management tool, PCT would test the cycle from project creation, task assignment, progress tracking, to project completion and reporting. The test would validate that the system allows seamless management of projects, task updates are reflected in real-time, and final reports can be generated without issues.

## 11- **Data Cycle Test (GCT) and Syntactic Test (SYN)**

These tests are about verifying the data integrity throughout its lifecycle in the system and ensuring the system can handle both valid and invalid formats. Data Cycle Testing checks the flow and processing of data across the system, while Syntactic Testing ensures that data in various formats is correctly parsed and handled by the system.

> **Example for GCT**: For a web-based customer support ticketing system, GCT would track a support ticket from submission through to resolution and closure, ensuring that customer data and ticket details are preserved and processed accurately throughout the life of the ticket.

> **Example for SYN**: For the same ticketing system, syntactic testing might involve submitting tickets with various data formats, such as text inputs, file attachments, and form data, to ensure the system parses and stores the data correctly. It would also intentionally submit poorly formatted data to test the system’s error handling capabilities.

---




# Insightful Summary of Eleven Test Design Techniques

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
