# Salesforce CRM Project: NATION VISA

This repository contains the practical work for a Customer Relationship Management (CRM) course project, implemented on the Salesforce platform. The project, named "NATION VISA", demonstrates a custom Salesforce application built to manage applicants, accounts, and related processes.

This project showcases a progressive build of a Salesforce application, covering data modeling, security, business logic with Apex, and custom user interface development with Lightning Web Components.

**Author:** Prajjwal Mohan
**Batch:** A3-47

## Technologies Used

* **Platform:** Salesforce (Lightning Experience)
* **Back-End:** Apex
* **Front-End:** Lightning Web Components (LWC), HTML, JavaScript
* **Data:** SOQL (Salesforce Object Query Language), DML (Data Manipulation Language)
* **Tools:** Salesforce Setup, Developer Console

## Project Practicals Overview

This repository includes the following practical modules:

### 1. Practical 1: Data Model and Validation Rules
* **File:** `A3_47_CRM_01 (1).pdf`
* **Description:** This practical involved setting up the initial data model, including custom objects like "Applicant".
* **Key Features:**
    * Implementation of various validation rules to ensure data integrity.
    * Example Rule: Prevent an 'Applicant' record from being saved if the 'Pan Card' field is blank.
    * Example Rule: Prevent an 'Applicant' from being saved if the 'DOB Month' is "August".
    * Example Rule: Complex validation on the 'Account' object to prevent saving if 'Rating' is "Hot" or "Cold" while 'SLA' is "Gold" or "Platinum" and 'SIC Code' is blank.

### 2. Practical 3: Security & Sharing
* **File:** `Prajjwal_CRM_A3_47_Pr3 (1).pdf`
* **Description:** Focused on configuring the security and sharing model for the application.
* **Key Features:**
    * Creation of custom user **Profiles** like "Data Entry Clerk" and "Passport Verification Officer".
    * Configuration of **Object Permissions** (Create, Read, Edit, Delete) for different profiles.
    * Setting **Field-Level Security (FLS)** to control the visibility and editability of specific fields.
    * Implementation of **Sharing Rules** to grant additional record access beyond the organization-wide defaults.

### 3. Practical 4: Apex DML Operations (CRUD)
* **File:** `CRM_A3_47_Pr4.pdf`
* **Description:** Introduced server-side logic using Apex to perform Data Manipulation Language (DML) operations.
* **Key Features:**
    * Created an Apex class (`ApplicantCRUD`) to handle business logic for the 'Applicant' object.
    * Implemented methods for **Create** (`createApplicant`), **Read** (`getApplicants`), **Update** (`updateApplicant`), and **Delete** (`deleteApplicant`) operations.

### 4. Practical 5: Apex Triggers
* **File:** `Prajjwal_A3_47_CRM_05.pdf`
* **Description:** Implemented an Apex Trigger to automate a business process based on a data change.
* **Key Features:**
    * Wrote an `after insert` and `after update` trigger (`AddressTrigger`) on the `Address__c` custom object.
    * **Logic:** When an address is saved with the 'City' set to "Nagpur", the trigger automatically updates the `Police_Verification__c` checkbox to `true` on the related parent 'Applicant' record.

### 5. Practical 6: Batch & Schedulable Apex
* **File:** `A3_47_CRM_06.pdf`
* **Description:** Explored asynchronous Apex for processing large data volumes.
* **Key Features:**
    * **Batch Apex:** Implemented a `Database.Batchable` class (`batch_acc_apex`) to find all 'Account' records with a 'Rating' of "Hot" and update them to "Cold".
    * **Schedulable Apex:** Created a `Schedulable` class (`TimerClass`) to invoke the batch job at a specified time, demonstrating automated job execution.

### 6. Practical 7: Lightning Web Components (LWC)
* **File:** `A3_47_CRM_Practical 7.pdf`
* **Description:** Developed a custom user interface component using the LWC framework.
* **Key Features:**
    * Built an LWC named `createAccountForm` to allow users to create a new 'Account' record.
    * **Component Structure:**
        * `createAccountForm.html`: The component's template with a `<lightning-card>` and `<lightning-input>`.
        * `createAccountForm.js`: The JavaScript controller to handle user input and button clicks.
        * `AccountController.cls`: An Apex controller with an `@AuraEnabled` method (`createAccountRecord`) to receive data from the LWC and perform the DML `insert` operation.

### 7. Practical 8: Reports & Dashboards
* **File:** `A3_47_CRM_08.pdf`
* **Description:** Focused on data analysis and visualization using Salesforce's built-in reporting tools.
* **Key Features:**
    * Creation of a custom **Report** named "New Accounts Report" to list account data.
    * Creation of a **Dashboard** to provide a visual summary of key metrics, such as "Dashboard on Acous".