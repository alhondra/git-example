# Test Overview
## Quality Goals

The entire team works together to manage product quality, with shared responsibility for test coverage through different perspectives. 
This document describes the test process for the Data Solutions team, including test planning and  coverage, responsibilities, defects, and QA review. 
However, the process should always align with our quality goals; continuous improvement is encouraged with quality goals in mind.

## Achronimus

 * TE - Test Engineer
 * QA - Quality Assurance
 * SE - Software Engineer (developer)
 * FVT - Functional Verification Test
 * FVTR - Functional Verification Test Regression
 * AC- Acceptance Criteria

## Test Engineering

At a high level, the following test engineering activities occur as part of each new development card. These are described in more detail in the remainder of this document.

1. Black Box Test coverage for the new feature is outlined by the TE 
2. Code implementation for the new feature is performed by the developer
3. Manual/ ad hoc testing for the new feature is executed by the TE when code is ready
4. Test review, to verify that the original black box test coverage is done
5. Defect documentation for any issues found
6. Story sign-off to ensure black box test coverage and behavior
7. Test planning for regression in the following sprint
 
## Test Traceability 
All tests require tags or annotations that tie back to the story, AC, or feature. 

Test Matrix: Decomposition of all User Acceptance requirements, Stories or Features in test cases. A list of functionality that will be tested. 
Each Functional Requirement will have a test Case. It is a Traceability Matrix. 

# QA Workflow
## Feature Development
Refer to the development document (**Reference TBD**) for an overview of the development process.

## Test Planning

### 1. Assignment
During the sprint, test engineers (TE) will be assigned several Story cards and defects for black box test coverage. (Each card will have both a developer and a test engineer assigned.) If anything is unclear in the AC's, the TE should ask and discuss with the team and/or developer.

This black box test coverage should be prioritized based on card priority assigned during sprint planning as high, medium, low.
 
### 2. Test Coverage
Once the card is assigned to the TE, the test engineer will:
* Review the acceptance criteria of the cards/defects and generate black box test coverage as a Task in **VersionOne**.
* Test coverage will be determined based on acceptance criteria.
* Test matrix will be added within the **Test Coverage Task** in the VersionOne card/defect and will be a traceability Matrix that will link each acceptance criteria to the test cases in **Test Rail**.

### 3. Dev Coverage Review
After the TE team has completed the Test Coverage, the TE will:
 * Notify the developer via the VersionOne card conversation that the black box **Test Coverage Task** is ready
 * Review the coverage with the developer if needed                                

### 5. Test Creation
Manual Test Cases will be created in **Test Rail** tool using Gherkin language.
Test matrix created in VersionOne within the **Test Coverage Task** will be updated with the new Test Case IDs and links to Test Rail that were created for the test coverage of the card.

### 6. Development Continues
Once the code is implemented, merge request submitted, and code review completed, then the card will move into **Functional Test** status.

## Functional Test

**Functional Test** should be prioritized by the TE once the card goes into the **Functional Test** column. The **Functional Test** should be done by the test engineer who did the test planning for that card.  

### 1. Manual / Ad Hoc Testing

 1. The TE will use the production site URL to access to the instance to test.
    [Data Solutions](https://dataanalytics-dev.commerce.toshiba.com/app/main#/home)
 2. Based on the expected behavior, the TE will run through the planned tests cases manually to evaluate the feature from a user and requirements perspective. 
    *   If the test includes a Data Solutions Client, testing should be done against the specific client's Dashboards.
 3. The TE will run some exploratory tests and identify any issues:
     * If the issue is not related to the current card, but the product in general, then the TE will create a defect. (See the **Defects** section below for details.)
     * If the issue is related to the current card, then the TE will:
         * Discuss with the developer and agree on the expected behavior. Involve managers and product owners if needed.
         * After reaching agreement on the need for changed behavior, the TE will add comments in the card conversation section to summarize the behavior concerns/expectations, tag the developer in the conversation, and move the card back to **In Progress**. (Once the issue has been addressed, the developer will move the card back to **Functional Test** where this process will reset.)
         * The developer will commit new changes to address these issues under the same VerionOne story within the same sprint. This cycle will only happen one time. If there are new issues or issues that can't be resolved quickly, these will be opened as defects for the next sprint and the story will be moved to Accepted in VersionOne. (See the **Defects** section below for details.)
     

### 2. Card Review
  
 * If the TE has any questions or concerns with the product behavior, tests, or coverage, then:
 
    1. TE should discuss with the developer and involve managers and product owners if needed. 
    2. After reaching agreement on any changes needed to the tests, the TE will add comments in the card conversation section to summarize the concerns/expectations, tag the developer in the conversation, and move the card back to **In Progress**. 
    3. Once the issue has been addressed, the developer will move the card back to **Functional Test** where this process will reset.


 
## Defect Management


### Defects should be created when:
 * An issue is found outside the scope of the card under test.
 * The team agrees to close a card with an issue left unresolved.

### Defect Report
 * Defects will be reported in Version One tool using the [Data Solutions defect template](https://www6.v1host.com/ToshibaGCS/defect.mvc/Summary?oidToken=Defect:911619)
 * Defects should contain the following information:
	#### Title:
    * Nomenclature:
    * DS - [Dashboard/Section/Widget] - A brief description of the issue
	#### Description:
    * Short explanation that describes the problem at a high level (Function area, problem type)
	#### Recreate Steps:
    * Pre-Requisites (Link to the enviroment to test)
	* User credentials (if needed)
	* Date/Time when evidence was taken
	* Steps to reproduce
	* Additional Details like screenshots, UI theme, browser, etc.
	* Test environment (if relevant to recreate)
	* Actual Result
	* Evidence (screenshots, logs, Diagnostic information: Error code, error, description, etc)
	#### Expected Behavior:
	* What's the result that we are expecting.
	#### Sprint:
	* When defect was found at the very end of the sprint, we will choose to select the next sprint.
	* When defect was found and there's a time frame and developer agrees to include it in same sprint, we will choose current sprint.
	#### Team:
	* (leave blank)
	#### Epic item:
	* If there's an Epic Item related to this defect, please indicate it.
	#### Estimated points: 
	* 0.25
    #### Client:
    * In case this specific defect is affecting a particular client, please indicate so, if it affects all, leave blank.
	#### Priority:
    * Please refer to Defect Priority information below.
	#### Severity:
    * Please refer to Defect Priority information below.
	#### Phase found:
    * Exploratory Test, Automated test, Regression, FVT, etc.
	#### Assigned Resource:
    * Developer that will fix the issue and TE that will be testing the fix (the creator of the defect).

### Defect Process

 1. Create a new defect using the [Data Solutions defect template](https://www6.v1host.com/ToshibaGCS/defect.mvc/Summary?oidToken=Defect:911619) in **VersionOne**.
 2. In **VersionOne**, Add a **Test Coverage Task** to the Defect card for the verification of the fix:
    * The TE will create the coverage Test Matrix and the **BDD's**  to cover the verification of the defect, and the Test Matrix will indicate the traceability to the corresponding Test Case ID from **Test Rail**. 
 3. In **Test Rail**, assign the **VersionOne Defect ID** to the corresponding Test Case(s).
    * **Step 1**
        * If there is no test case that covers the verification of this Defect, then proceed creating a new test case(s) to cover this verification.
        * If there is already a test case(s) that covers the verification of this Defect, no new test cases need to be created.
    * **Step 2**
        * Add **DefectID** to the Test Case(s) in **Test Rail**
	* **Step 3**
        * Mark the corresponding Test Case(s) in **Test Rail** as Status Failed for the current Test Run.
 4. Typically, as defect cards are assigned and fixed, they will go through the test planning and Functional Test process (Please refer to **Defect Status** section below for more details).
 5. Once the Defect has been fixed and verified by the TE:
    * **In VersionOne** TE will move the Defect card to Done.
    * **In Test Rail** TE will mark the Test Case as Pass for tue current Test Run.
 
### Defect Status
1. **(None):** Defect is in backlog but is not ready to be included in the sprint. During the daily scrum meetings the TE can agree with the team whether the defect will be indicated as (none) in case the defect will not be included in the current sprint but will be fixed in a future sprint.
2. **Ready:** Defect is planned for the sprint and is ready to be taken by a developer to proceed with the implementation of the fix.
3. **In Progress:** Defect is being fixed by the developer.
4. **Functional Test:** Defect fix was completed by the developer and TE is now re-testing defect.
5. **Done:** When fix passes testing by the TE, the defect is moved to Done status, if the fix fails testing, the TE moves the defect back to "In Progress" status.
6. **Accepted:** The defect can be moved to "Accepted" once the TE team has resumed testing for the current sprint.

### Defect Severity
The extent of damage done by the defect. It indicates how badly the defect affects the functionality of the software product.

1. **Critical:**
* There is no work around.
* Total failure of the system 
* Unrecoverable data loss.
* Affects multiple users, performing critical functionality where there is no work around.
* Defect prevents the product from being released.
2. **Severe:**
* There is no workaround or a work around is available however this is unsatisfactory for daily services and causes an impact on productivity.
* Defect presence makes it difficult to improve system test coverage and so prevents uncovering of potentially more serious issues.
* Limited use in Production - some requirements not met.
3. **Moderate:**
 * An alternative clear reasonable work around is available for the following issue types:
* Defect impacts only noncritical aspects of the system or functions that enhance usability.
* The product could be released if the defect is documented, but the defect presence may cause user dissatisfaction and so training or user notification may be required.
* Defect presence causes issues to the test team
4. **Minimal:**
* Defect is of minor significance. A work around exists or, if not, the impact is not significant.
* Could release with the defect, as most users would be unaware of the defect's existence or only sightly disatisfied.
* In the case of very minor defects (Cosmetic) the problem can be ignored.


### Defect Priority
Something that is defined by business rules. It defines how important the defect is and how early it should be fixed.

1. **High:**
* Must fix for the current release.
* Focussed with the present critical issues preventing any further QA activities.
* Root cause analysis must be performed as part of the investigation to minimize recurrence of defect in future releases.
2. **Medium:**
* Should be fixed for the next release if time allows.
* Useful for overall quality but no real value added to functionality /usability, etc.
3. **Low:**
* Generally associated with Low severity.
* Fix if and only if development and TE team have bandwidth; and no other higher priority issues exist, with no risk on regression.
     

## Story SignOff
### Definition of Done
When a card can be marked as Done?
Below is the criterion that must be met in order to mark the status of a card as **Done**:

1. All acceptance criteria is met.
2. All acceptance criteria has been covered with Test Cases in Test Rail.
3. 100% of all FVT have been attempted using integrated code or fixes.
	Please note: It is recommended that tests executed during FVT with fixes are re-executed during FVTR.
4. All valid defects found during FVT have been recorded in Version One as Defect Cards.
5. At least 100% of all test execution is complete. Complete is defined as:
	a. Tests which have executed successfully. - or- 
	b. Tests which are unsuccessful (due to deferred issue) have agreed upon:
		i. Issue answered
		ii. Fix date for a future sprint
6. All Blocker and High severity issues have been documented via defect, fixed, integrated, built and verified.
7. Plans are in place to reach 100% completion and include the following details:
	a. Defects written and answered.
	b. Verification plans in place to test Defects.

 The TE will move the Story card to Done.

### Acceptance of a Card
Once the Story Card is marked as Done, A Story Sign Off **Task** will be added to the User Story.
* TE may use the Story Sign Off template created for Data Solutions project.
* In case there are opened defects from this User Story card, they will be listed in this sign off, for reference.
At the end of the Sprint, during the Demo, if the team agrees with the current implementation of the Cards with status **Done** then they can move it to **Accepted**.


## Regression Maintenance 
When tests fail during the builds, the QA team will review the failing scenarios and open a defect when necessary. (See Defects section above.)

## Exploratory Testing
As features are added, test engineers should perform general product exploratory testing on the deployed version of the project. 
A Task in Version One Card should be created for Exploratory Testing and The TE should allocate several hours of exploratory testing each week.
After each Exploratory Session, QA will add an Exploratory Testing Report and attach it to the Version One Card within the Exploratory Testing task.

## Metrics

|CTQ Description|Metric|
| ---------- | ----------- |
|Test Cases Created|Number of Test Cases designed by sprint
||  # manual - count records in Test Rail |
|Test Cases Executed|Number of Test Cases executed by sprint
||  # manual
|Total Defects|Number of Defects
||  # created - count defects opened in VersionOne|

