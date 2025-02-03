# **Manual Test Plan for Scopex Money**

## **1. Introduction**
This test plan covers manual testing for the following functionalities of the Scopex Money mobile application:
- **User Registration**
- **Login**
- **Adding a Recipient**
- **Logout**

The goal is to ensure these features work as expected before proceeding with automation testing.

---

## **2. Test Approach**
The testing approach includes:
- Identifying key test scenarios.
- Defining required test data and preconditions.
- Verifying expected outcomes for each scenario.
- Setting up the appropriate test environment.
- Documenting assumptions, risks, and constraints.

---

## **3. Test Scenarios and Cases**

### **3.1 User Registration**
**Objective:** Verify that a user can successfully register on Scopex Money.

#### **Test Cases**
| Test Case ID | Scenario | Steps | Expected Result |
|-------------|-----------|--------|-----------------|
| REG-001 | Verify registration with valid details | Enter valid name and email, click "Sign Up". | User should be successfully registered. |
| REG-002 | Verify "Continue with Google" | Click "Continue with Google" and select an account. | User should be registered successfully. |
| REG-003 | Verify registration with a referral code | Enter valid name, email, and referral code, click "Sign Up". | Referral benefits should be applied (if any). |
| REG-004 | Register with an empty name field | Leave the name field empty and submit. | "Name is required" error should be displayed. |
| REG-005 | Register with an empty email field | Leave the email field empty and submit. | "Email is required" error should be displayed. |
| REG-006 | Register with both fields empty | Leave both fields empty and submit. | Error messages should be displayed for both fields. |
| REG-007 | Register with an invalid email format | Enter an email like "abc@com" and submit. | "Enter a valid email address" error should be displayed. |
| REG-008 | Register with special characters in name | Enter name as "@John#" and submit. | "Name cannot contain special characters" error should be displayed. |
| REG-009 | Register with a very long name | Enter a name longer than 50 characters. | "Name is too long" error should be displayed. |
| REG-010 | Register with an already registered email | Enter an email already used for registration. | "Email is already registered" error should be displayed. |
| REG-011 | Verify case sensitivity in email field | Register using "Test@Email.com" and then try with "test@email.com". | System should recognize it as the same email. |
| REG-012 | Verify registration without clicking "Sign Up" | Enter valid details but do not click "Sign Up". | Registration should not proceed. |

---

### **3.2 Login**
**Objective:** Verify that a user can log in successfully and handle invalid inputs properly.

#### **Test Cases**
| Test Case ID | Scenario | Steps | Expected Result |
|-------------|-----------|--------|-----------------|
| LOG-001 | Verify login with valid credentials | Enter valid email and password, click "Log in". | User should be logged in. |
| LOG-002 | Verify login with incorrect password | Enter a wrong password. | "Incorrect password" error should be displayed. |
| LOG-003 | Verify login with an unregistered email | Enter an unregistered email and submit. | "No account found" error should be displayed. |
| LOG-004 | Verify login with empty fields | Leave both fields empty and submit. | Error messages should be displayed for both fields. |
| LOG-005 | Verify login with an invalid email format | Enter an email like "abc@com" and submit. | "Enter a valid email address" error should be displayed. |
| LOG-006 | Verify "Continue with Google" | Click "Continue with Google" and select an account. | User should be logged in successfully. |
| LOG-007 | Verify login session expiration | Stay inactive for a long time and try accessing a secure page. | User should be logged out automatically. |
| LOG-007 | Verify 2 user sessions are active in 2 different systems on same time | Enter a valid email and password in 2 different systems simultaneously, and click "Log in." | Do not allow login with the second session if the first is still active. |

---

### **3.3 Adding a Recipient**
**Objective:** Verify that a recipient can be added successfully.

#### **Test Cases**
| Test Case ID | Scenario | Steps | Expected Result |
|-------------|-----------|--------|-----------------|
| REC-001 | Add a recipient with valid details | Enter name, bank details, and submit. | Recipient should be added. |
| REC-002 | Add a recipient with missing details | Leave required fields blank and submit. | Error message should be displayed. |
| REC-003 | Add a recipient with invalid bank details | Enter incorrect bank details and submit. | "Invalid bank details" error should be displayed. |
| REC-004 | Add a recipient with special characters in name | Enter name as "@John#" and submit. | "Name cannot contain special characters" error should be displayed. |
| REC-005 | Add a duplicate recipient | Add the same recipient again. | "Recipient already exists" error should be displayed. |
| REC-006 | Verify recipient deletion | Select a recipient and delete it. | Recipient should be removed from the list. |

---

### **3.4 Logout**
**Objective:** Verify that the logout functionality works correctly.

#### **Test Cases**
| Test Case ID | Scenario | Steps | Expected Result |
|-------------|-----------|--------|-----------------|
| LOGOUT-001 | Verify successful logout | Click on "Logout". | User should be logged out and redirected to the login screen. |
| LOGOUT-002 | Verify session expiration | Stay inactive and try accessing a secure page. | User should be logged out automatically. |

---

## **4. Test Data Requirements**
- Valid and invalid email formats for registration.
- Test bank details for recipient addition.

---

## **5. Test Environment**
- **Devices:** Android & iOS
- **OS Versions:** Latest and one previous major version
- **Browsers:** Chrome, Safari
- **Network:** Wi-Fi and Mobile Data

---

## **6. Assumptions & Constraints**
- The app should have stable internet connectivity.
- Users should receive OTPs without delays.
- The test will be conducted on a staging/pre-production environment (if available).

---

## **7. Acceptance Criteria**
- **User Registration:** The user should be successfully registered.
- **Login:** The user should be able to log in.
- **Adding a Recipient:** The recipient should be successfully added.
- **Logout:** The user should be logged out.

---

## **8. Deliverables**
- **Manual Test Plan:** This document.
- **Automated Test Scripts:** To be developed using JavaScript/TypeScript.
- **Bug Report:** Issues found during exploratory testing.

---

