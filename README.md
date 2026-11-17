# iSERVU – Ride-Sharing Platform | QA & Manual Testing

<p align="center">
  <strong>Quality Assurance Documentation</strong><br>
  Manual Testing • Functional Testing • Regression Testing • Bug Reporting
</p>

<p align="center">
  <a href="https://www.iservu.app/">Project Website</a>
  &nbsp;|&nbsp;
  <a href="https://drive.google.com/drive/folders/1Aw_Plp_UkMqo0IybBZ7KvfRJ1whjmEUU?usp=drive_link">App Build (Google Drive)</a>
</p>

---

## 1. Project Overview

**iSERVU** is a ride-sharing platform that connects riders with drivers through on-demand and scheduled ride services. Riders can request an immediate ride or schedule a ride for a future date and time. Drivers receive ride requests and notifications through the Driver App.

The platform also includes an AI Assistant that allows users to communicate through a chatbot and book rides automatically. In addition to ride booking, iSERVU provides supporting services and safety, pricing, and notification features such as parcel delivery, surge pricing, rush-hour information, traffic alerts, weather alerts, and SOS alerts.

### Project Information

| Item | Details |
|---|---|
| Project Name | iSERVU |
| Project Type | Ride-Sharing / Ride-Hailing Platform |
| Website | https://www.iservu.app/ |
| Main Applications | Rider App, Driver App, Admin Panel |
| QA Documentation | Manual Testing & Bug Reporting |
| Platforms Referenced in Bug Reports | iOS, Android, Web / Admin Panel, Backend |

## 2. Project Modules

### Rider App

The Rider App allows users to request rides, schedule future trips, manage payments, communicate with drivers, and access additional services.

Key areas covered by the project requirements and QA reports:

- User registration, login, and authentication
- Pickup and drop-off location selection
- Regular ride requests
- Scheduled ride booking
- Driver assignment and ride status updates
- Ride details, trip history, and invoices
- Driver calling and in-app communication
- Card, wallet, and cash payment options
- Wallet and points/rewards
- Saved places
- Parcel delivery
- AI Assistant and chatbot-based ride booking
- Push notifications and service alerts
- SOS and safety-related features

### Driver App

The Driver App enables approved drivers to receive and manage ride requests, complete trips, handle scheduled rides, and monitor their earnings and account information.

Key areas covered:

- Driver registration and document submission
- Driver approval and account status notifications
- Online/offline availability
- Incoming regular ride requests
- Scheduled ride notifications and dispatch
- Accepting and managing trips
- Rider communication and calling
- Parcel delivery requests
- Earnings, payouts, and wallet
- Driver ratings and performance statistics
- Cancellation-rate information
- Traffic alerts and other notifications
- Help Center and FAQs
- SOS and safety-related features

### Admin Panel & Backend

The Admin Panel and backend support platform configuration, user and driver management, ride operations, payment settings, pricing, and notification services.

Key areas covered by the QA reports:

- Dashboard and platform settings
- Rider and driver profile management
- Ride and parcel-related configuration
- Payment method configuration
- Surge pricing
- Parcel pricing
- Points and rewards configuration
- Payout-related settings
- SOS alert and map settings
- Weather alert configuration
- AI push notification scheduling
- Broadcast push notifications
- Email and SMS configuration
- Google Cloud configuration
- Banner management

---

## 3. Core Ride Booking Workflows

### 3.1 Regular Ride Request

A regular ride is an on-demand booking initiated by a rider.

**Expected high-level flow:**

1. Rider opens the Rider App.
2. Rider selects pickup and destination locations.
3. The app displays the applicable ride/service options and fare estimate.
4. Rider selects a payment method.
5. Rider confirms the ride request.
6. The system sends the request to eligible/available drivers.
7. A driver receives the request notification.
8. The driver accepts the request.
9. Rider receives the driver and trip information.
10. The ride progresses through the relevant trip statuses.
11. The trip is completed and the applicable payment process is finalized.

**QA focus:**

- Pickup and drop-off validation
- Fare calculation and pricing consistency
- Driver request delivery
- Request acceptance and rejection
- Ride status synchronization
- Rider and driver notifications
- Payment processing
- Trip history and invoice generation

### 3.2 Scheduled Ride

A scheduled ride allows a rider to book a trip for a future date and time. The driver should receive the relevant scheduled-ride notification/dispatch according to the system's configured workflow.

**Expected high-level flow:**

1. Rider selects pickup and destination.
2. Rider chooses the scheduled ride option.
3. Rider selects a future date and time.
4. Rider reviews the ride details and payment option.
5. Rider confirms the scheduled booking.
6. The scheduled ride is saved in the system.
7. The driver is notified through the scheduled-ride dispatch workflow.
8. The driver can view the scheduled ride information.
9. The ride is handled at the scheduled time according to the configured process.

**QA focus:**

- Past-date and invalid-time validation
- Correct timezone handling
- Scheduled booking confirmation
- Driver notification and dispatch
- Scheduled ride card information
- Rescheduling and cancellation
- Scheduled ride payment behavior
- Rider/driver/admin status consistency

---

## 4. AI Assistant & Intelligent Features

### AI Assistant – Chatbot Ride Booking

The platform includes an AI Assistant that allows users to communicate with a chatbot and book a ride automatically.

**Intended user flow:**

1. User opens the AI Assistant.
2. User communicates the ride requirement through the chatbot.
3. The assistant gathers or confirms the required trip information.
4. The system prepares the ride request.
5. The user proceeds with the booking confirmation and applicable payment process.

**QA considerations:**

- Chatbot availability and response handling
- Correct interpretation of pickup and destination details
- Missing or ambiguous information handling
- Fare and ride-detail accuracy
- Booking confirmation before creating a ride
- Duplicate or unintended ride creation prevention
- Error handling when ride booking fails
- Correct synchronization with the regular ride workflow

### AI Push Notifications

AI-based push notification functionality is included in the project requirements and the Admin & Backend bug report.

QA considerations include notification scheduling, delivery, message accuracy, and correct targeting. The exact AI decision rules and personalization behavior should be validated against the approved product requirements.

---

## 5. Additional Platform Features

| Feature | Description | QA Focus |
|---|---|---|
| Rush Hour | Provides rush-hour-related information to support ride operations. | Time-window accuracy, display, and relevant notifications |
| Traffic Alert | Provides traffic-related alerts to riders and/or drivers. | Alert accuracy, timing, and delivery |
| Parcel Delivery | Supports parcel-related service requests and delivery workflows. | Parcel booking, pricing, payment, OTP, status, and driver earnings |
| Surge Pricing | Applies configured surge pricing when applicable. | Pricing rules, active periods, fare calculation, and consistency |
| SOS Alert | Provides an emergency alert feature. | Trigger behavior, alert delivery, location/map handling, and reliability |
| AI Push Notification | Supports AI-based push notification functionality. | Scheduling, targeting, content, and delivery |
| Weather Alert | Notifies both riders and drivers about relevant bad-weather conditions. | Weather condition handling, alert timing, and delivery to both apps |

**Note:** The feature descriptions above reflect the project information provided for this documentation. Detailed business rules, thresholds, triggers, and configuration behavior should be validated against the approved SRS or client requirements.

---

## 6. Payment Methods

iSERVU supports three payment methods.

### 6.1 Online Payment – Card

Riders can pay for rides using a supported payment card through the configured payment gateway.

**QA focus:**

- Card payment selection
- Payment gateway redirection or payment interface
- Successful and failed transactions
- Payment confirmation
- Prevention of ride completion without required payment
- Correct transaction and trip status synchronization

### 6.2 Wallet Payment

Riders can use their available wallet balance to pay for a ride or applicable service.

**QA focus:**

- Wallet balance validation
- Sufficient and insufficient balance scenarios
- Wallet debit after successful booking/payment
- Transaction history
- Duplicate debit prevention
- Correct wallet balance synchronization

### 6.3 Cash Payment

Riders can select cash as the payment method and pay according to the platform's cash-payment workflow.

**QA focus:**

- Cash payment selection
- Correct payment-method indicator
- Ride completion and payment status
- Driver earnings and applicable dues
- Correct trip records in the Admin Panel

---

## 7. QA & Testing Scope

The QA scope is organized around the Rider App, Driver App, shared app functionality, Admin Panel, and backend services.

### Testing Types

| Testing Type | Coverage |
|---|---|
| Functional Testing | Validate individual features against expected behavior. |
| End-to-End Testing | Validate complete rider-to-driver ride and parcel workflows. |
| Integration Testing | Verify communication between apps, backend, payment services, and notification services. |
| Regression Testing | Recheck existing functionality after bug fixes and changes. |
| Smoke Testing | Verify critical application flows after a new build or deployment. |
| UI Testing | Validate labels, layouts, screen behavior, and user-facing messages. |
| Compatibility Testing | Validate relevant app behavior on iOS and Android. |
| API Testing | Validate backend requests, responses, status codes, and data consistency where API access is available. |
| Notification Testing | Validate push, email, and SMS notification behavior. |
| Payment Testing | Validate card, wallet, and cash payment workflows. |
| Stability Testing | Check app crashes, intermittent behavior, and critical flow reliability. |

### Critical End-to-End Scenarios

- Rider requests a regular ride and an available driver receives it.
- Driver accepts a ride and both apps display consistent trip information.
- Rider schedules a future ride and the driver receives the scheduled-ride notification according to the configured workflow.
- Rider completes a ride using card payment.
- Rider completes a ride using wallet payment.
- Rider selects cash and the trip follows the configured cash-payment process.
- Rider books a parcel delivery and the parcel workflow is completed.
- AI Assistant gathers ride details and creates a booking only after the required confirmation.
- SOS alert is triggered and the configured alert/response workflow is executed.
- Weather, traffic, rush-hour, surge, and AI notifications behave according to their configured rules.

---

## 8. Bug Report Documentation

Four bug-report trackers were reviewed for this QA documentation.

| Bug Report | Bug ID Range | Reported Issues | Marked Done |
|---|---|---:|---:|
| Rider App | RA-01 – RA-23 | 23 | 23 |
| Driver App | DA-01 – DA-22 | 22 | 21 |
| Rider & Driver Apps | RD-01 – RD-38 | 38 | 37 |
| Admin & Backend | AD-01 – AD-19 | 19 | 19 |
| **Total** | — | **102** | **100** |

**Status interpretation:** 100 issues have `Done` in the `Final_Status` column. Two issues have a blank `Final_Status` in the supplied trackers. A blank status is not treated as resolved or pending without further confirmation.

### Bug Report Coverage

**Rider App**
- Ride pricing and fare display
- Invoices and trip details
- Driver calling
- Card payment gateway
- Points and rewards
- Scheduled ride payment
- Saved places and service selection
- Wallet and UI behavior
- Localization and notifications
- AI smart suggestions and estimates

**Driver App**
- Ride request delivery and acceptance
- App stability
- Driver approval notifications
- Registration document labels
- Scheduled ride dispatch and ride cards
- Parcel delivery and earnings
- Driver statistics and cancellation rate
- Traffic alerts
- Wallet, dues, and payout-related screens
- Help Center and profile behavior

**Rider & Driver Apps**
- Push notifications
- Google sign-in
- Branding and terminology
- Authentication and profile behavior
- Scheduled rides and timezones
- Parcel delivery OTP and payment
- Chat notifications, presence, and read receipts
- Trip details and timestamps
- Payment indicators
- Deep links and app download behavior
- Help Center, legal text, and localization

**Admin & Backend**
- Payout methods and settings
- Ride number format
- Points and rewards backend
- Payment methods
- Parcel pricing
- Surge pricing
- SOS alert and map settings
- Weather alerts
- AI push notification scheduling
- Email, SMS, and broadcast notifications
- Profile synchronization
- Dashboard and banners
- Google Cloud configuration

---

## 9. QA Bug Reporting Standards

Each reported issue should clearly describe the problem and provide enough information for the development team to reproduce and resolve it.

The supplied trackers use the following fields:

- Bug ID
- Reported Date
- Module
- Platform
- Bug Title
- Description
- Steps to Reproduce
- Expected Result
- Actual Result
- Severity
- Priority
- QA Status
- DEV Status
- Attachment
- Reported By
- Final Status

### Bug Lifecycle

1. Identify the issue during testing.
2. Reproduce the issue and confirm its behavior.
3. Record clear steps, expected result, and actual result.
4. Assign severity and priority.
5. Share the issue with the development team.
6. Verify the fix after a new build or deployment.
7. Update QA and final status based on the verification result.
8. Reopen the issue if the problem still exists.

---

## 10. Important QA Considerations

- Validate ride status consistency across Rider App, Driver App, Admin Panel, and backend.
- Verify that a ride request is not assigned or accepted incorrectly by multiple drivers.
- Validate scheduled ride date/time and timezone behavior.
- Confirm that fare calculations match the configured pricing rules.
- Verify payment status before marking a paid trip as successfully completed.
- Check wallet balance and transaction records after each wallet transaction.
- Verify parcel delivery status and OTP validation.
- Confirm that push notifications reach the correct user and platform.
- Test SOS behavior carefully in a controlled test environment.
- Validate surge, rush-hour, traffic, and weather rules using approved configuration and test data.
- Verify AI Assistant booking details before a ride is created.
- Check app stability during critical ride-request and trip-management operations.
- Re-test previously fixed issues during regression testing.

---

## 11. Test Environment & Dependencies

The following areas may require access or test configuration to execute complete QA scenarios:

- Rider App test build
- Driver App test build
- Admin Panel access
- Backend/API test environment
- Test rider and driver accounts
- Configured service zones and vehicle types
- Payment gateway test credentials
- Push notification configuration
- Maps and location services
- Email and SMS configuration
- Approved AI Assistant test scenarios
- Test data for scheduled rides, surge pricing, rush hours, traffic, and weather alerts

Actual environment URLs, build numbers, device details, API credentials, and test-account information should be maintained separately and should not be committed to a public repository.

---

## 12. Project Website

**iSERVU:** https://www.iservu.app/

---

## 13. Conclusion

This repository documentation summarizes the iSERVU ride-sharing platform, its major user-facing features, payment methods, core workflows, and QA coverage. It also records the scope of the four supplied bug-report trackers.

The purpose of QA is to help ensure that riders can book and manage rides reliably, drivers can receive and complete trips correctly, and administrators can manage the platform with consistent data and dependable supporting services.

**QA Documentation – iSERVU Ride-Sharing Project**
