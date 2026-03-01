# Module 5: Intent Form & Clarity Call Appointment Scheduling

## Module Overview

This module automates the process of collecting user intent through forms and scheduling clarity calls with potential clients. It integrates form submission, appointment booking, calendar synchronization, email notifications, and lead tracking into a seamless workflow. The system is designed to minimize manual intervention while maintaining professional communication with prospects.

## Objectives

- Capture user intent and qualification information through structured forms
- Enable self-service appointment scheduling for clarity calls
- Automatically sync appointments with business calendar
- Send confirmation and reminder emails to reduce no-shows
- Store and track lead information in a centralized CRM system
- Provide a smooth user experience from initial contact to scheduled appointment

## Submodule Breakdown

### 5.1 Intent Form
Collects user information, business goals, and qualification data before scheduling a call.

### 5.2 Intent Classification
Placeholder for future implementation of automated lead scoring and classification.

### 5.3 Appointment Booking
Provides an interface for users to select available time slots and book clarity calls.

### 5.4 Calendar Sync
Ensures all booked appointments are reflected in the business calendar in real-time.

### 5.5 Email Confirmation & Reminders
Automatically sends confirmation emails upon booking and reminder emails before scheduled calls.

### 5.6 CRM / Lead Storage
Stores all form submissions and appointment data for tracking and follow-up purposes.

## Technology Stack

| Submodule | Technology | Purpose |
|-----------|-----------|---------|
| 5.1 Intent Form | Google Forms, React | Form creation and data collection |
| 5.2 Intent Classification | Not Implemented | Future lead scoring capability |
| 5.3 Appointment Booking | Calendly (Free Plan) | Self-service scheduling interface |
| 5.4 Calendar Sync | Calendly + Google Calendar | Automatic calendar synchronization |
| 5.5 Email Notifications | Calendly Email System | Automated confirmations and reminders |
| 5.6 CRM / Lead Storage | Google Sheets + Zapier (Free) | Lead tracking and data storage |

## System Architecture

The system follows a linear pipeline architecture where each component handles a specific stage of the user journey:

- **Entry Point**: Instagram bio link directs users to the intent form
- **Data Collection Layer**: Google Forms or React form captures user information
- **Storage Layer**: Google Sheets stores form responses and appointment data
- **Scheduling Layer**: Calendly provides booking interface and calendar management
- **Communication Layer**: Calendly handles all email communications
- **Integration Layer**: Zapier connects form submissions to CRM updates

## End-to-End Workflow

1. **User Discovery**: Potential client clicks link in Instagram bio
2. **Form Submission**: User lands on intent form (Google Forms or React-based landing page)
3. **Data Capture**: User fills out form with contact details, business information, and goals
4. **Initial Storage**: Form response is automatically saved to Google Sheets
5. **Redirect to Booking**: Upon form submission, user is redirected to Calendly booking page
6. **Appointment Selection**: User views available time slots and selects preferred appointment time
7. **Calendar Update**: Calendly automatically syncs appointment to Google Calendar
8. **Confirmation Email**: Calendly sends immediate confirmation email to user and business owner
9. **CRM Update**: Zapier automation triggers to update Google Sheets with appointment details
10. **Reminder Emails**: Calendly sends automated reminder emails before the scheduled call
11. **Call Execution**: Clarity call takes place at scheduled time

## Integration with Other Project Modules

- **Module 1-3 (Instagram Engagement)**: Qualified leads from Instagram are directed to this module via bio link
- **Module 4 (DM Automation)**: Can reference appointment booking link in automated responses
- **Module 6 (Post-Call Follow-up)**: Receives appointment data and call outcomes for follow-up sequences
- **Module 7 (Analytics)**: Provides conversion data from form submission to booked appointments

## Automation Flow Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                        Instagram Bio Link                        │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│              Landing Page / Intent Form                          │
│              (Google Forms or React)                             │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│                   User Fills Intent Form                         │
│         (Name, Email, Business Type, Goals, etc.)                │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│              Form Data Stored in Google Sheets                   │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│              User Redirected to Calendly                         │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│              User Selects Time & Books Call                      │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│         Calendly Syncs with Google Calendar                      │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│    Calendly Sends Confirmation Email (User + Business Owner)     │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│    Zapier Updates Google Sheets with Appointment Details         │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│         Calendly Sends Reminder Emails Before Call               │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│                    Clarity Call Conducted                        │
└─────────────────────────────────────────────────────────────────┘
```

## Setup Instructions

### Prerequisites
- Google account for Forms, Sheets, and Calendar
- Calendly account (Free plan)
- Zapier account (Free tier)
- Instagram business account with bio link capability

### Step 1: Create Intent Form
1. Create a Google Form with fields: Name, Email, Phone, Business Type, Current Challenges, Goals
2. Configure form to store responses in a Google Sheet
3. Alternatively, build a React form component that submits to Google Sheets via API

### Step 2: Configure Calendly
1. Sign up for Calendly and create an event type for "Clarity Call"
2. Set duration (typically 30-60 minutes)
3. Configure availability hours and buffer times
4. Connect Calendly to Google Calendar under Settings > Calendar Connections
5. Enable email notifications for confirmations and reminders
6. Customize email templates with branding

### Step 3: Set Up Google Sheets CRM
1. Create a Google Sheet with columns: Timestamp, Name, Email, Phone, Business Type, Challenges, Goals, Appointment Date, Appointment Time, Status
2. Configure Google Forms to populate this sheet automatically

### Step 4: Configure Zapier Automation
1. Create a Zap: Trigger = "New Calendly Event"
2. Action = "Update Google Sheets Row" (match by email)
3. Map Calendly fields to Google Sheets columns
4. Test and activate the Zap

### Step 5: Create Redirect Flow
1. In Google Forms settings, set custom confirmation message with Calendly link
2. Or in React form, redirect to Calendly URL upon successful submission

### Step 6: Update Instagram Bio
1. Add link to intent form in Instagram bio
2. Use link shortener if needed (bit.ly, Linktree, etc.)

## Future Improvements

- Implement intent classification using natural language processing to prioritize high-value leads
- Add SMS reminders in addition to email notifications
- Integrate with full-featured CRM system (HubSpot, Salesforce)
- Build custom scheduling interface to reduce dependency on Calendly
- Add automated lead scoring based on form responses
- Implement A/B testing for form fields and conversion optimization
- Add video introduction on landing page to increase conversion rates
- Create automated follow-up sequences for no-shows
- Integrate payment collection for paid consultation calls
- Add calendar availability API to show real-time slots on landing page

## Security Considerations

- Ensure Google Forms and Sheets have appropriate access controls
- Use HTTPS for all form submissions and redirects
- Comply with GDPR and data privacy regulations for storing user information
- Regularly audit Zapier and Calendly integrations for unauthorized access
- Implement rate limiting on form submissions to prevent spam
- Store only necessary user information and establish data retention policies
- Use Calendly's built-in security features (email verification, CAPTCHA)
- Regularly backup Google Sheets data
- Avoid exposing API keys in client-side React code
- Implement proper error handling to avoid leaking system information
