# Use cases

## Map
## Map
  - [[UC-01] Account Creation (Verification Level 1)](#uc-01-account-creation-verification-level-1)
  - [[UC-02] Profile Specialization Setup](#uc-02-profile-specialization-setup)
  - [[UC-03] Phone Number Verification](#uc-03-phone-number-verification)
  - [[UC-04] Portfolio / Work Samples Upload](#uc-04-portfolio--work-samples-upload)
  - [[UC-05] Client Order History Review](#uc-05-client-order-history-review)
  - [[UC-06] Role Switching (Dual Profile)](#uc-06-role-switching-dual-profile)
  - [[UC-07] Identity Verification (KYC - Level 2)](#uc-07-identity-verification-kyc---level-2)
  - [[UC-08] Notification Preferences](#uc-08-notification-preferences)
  - [[UC-09] Job Posting (Basic Info)](#uc-09-job-posting-basic-info)
  - [[UC-10] Geolocation Tagging](#uc-10-geolocation-tagging)
  - [[UC-11] Visual Documentation (Photo Attachments)](#uc-11-visual-documentation-photo-attachments)
  - [[UC-12] Deadline Management](#uc-12-deadline-management)
  - [[UC-13] Pricing Model Selection](#uc-13-pricing-model-selection)
  - [[UC-14] Save Order as Draft](#uc-14-save-order-as-draft)
  - [[UC-15] Order Cancellation (Pre-selection)](#uc-15-order-cancellation-pre-selection)
  - [[UC-16] Applicant List Review](#uc-16-applicant-list-review)
  - [[UC-17] Real-time Job Feed](#uc-17-real-time-job-feed)
  - [[UC-18] Category Filtering](#uc-18-category-filtering)
  - [[UC-19] Map-based Search](#uc-19-map-based-search)
  - [[UC-20] Price Range Filtering](#uc-20-price-range-filtering)
  - [[UC-21] Favorites / Bookmarks](#uc-21-favorites--bookmarks)
  - [[UC-22] Client Exclusion (Hidden Feed)](#uc-22-client-exclusion-hidden-feed)
  - [[UC-23] Proximity Visibility](#uc-23-proximity-visibility)
  - [[UC-24] Category-Specific Push Notifications](#uc-24-category-specific-push-notifications)
  - [[UC-25] Job Application with Cover Letter](#uc-25-job-application-with-cover-letter)
  - [[UC-26] Price Counter-Offer (Bidding)](#uc-26-price-counter-offer-bidding)
  - [[UC-27] Performer Profile Review](#uc-27-performer-profile-review)
  - [[UC-28] Pre-Hire Messaging](#uc-28-pre-hire-messaging)
  - [[UC-29] Hire Confirmation](#uc-29-hire-confirmation)
  - [[UC-30] Hiring Confirmation Receipt](#uc-30-hiring-confirmation-receipt)
  - [[UC-31] Withdraw Application](#uc-31-withdraw-application)
  - [[UC-32] Real-time Status: "Heading There"](#uc-32-real-time-status-heading-there)
  - [[UC-33] Secure In-App Messaging](#uc-33-secure-in-app-messaging)
  - [[UC-34] Progress Photo Documentation](#uc-34-progress-photo-documentation)
  - [[UC-35] "Work Started" Trigger](#uc-35-work-started-trigger)
  - [[UC-36] "Task Completed" Declaration](#uc-36-task-completed-declaration)
  - [[UC-37] Job Approval (Closure)](#uc-37-job-approval-closure)
  - [[UC-38] Revision Request (Rework)](#uc-38-revision-request-rework)
  - [[UC-39] Message Read Receipts](#uc-39-message-read-receipts)
  - [[UC-40] No-Response Alert (Inactivity)](#uc-40-no-response-alert-inactivity)
  - [[UC-41] Payment Method Integration](#uc-41-payment-method-integration)
  - [[UC-42] Escrow Fund Reservation (Secure Deal)](#uc-42-escrow-fund-reservation-secure-deal)
  - [[UC-43] Performer Wallet Balance](#uc-43-performer-wallet-balance)
  - [[UC-44] Payout Request (Withdrawal)](#uc-44-payout-request-withdrawal)
  - [[UC-45] Transaction History and Receipts](#uc-45-transaction-history-and-receipts)


## [UC-01] Account Creation (Verification Level 1)
### 1. Description
**Actor:** User / Client

**Goal:** To gain access to the service features available for users with Verification Level 1.

### 2. Main Success Scenario (Happy Path)
  1. The User navigates to the registration form.
  2. The User enters the required information: Nickname, Email, Password, and Phone Number.
  3. The User clicks the "Sign Up" button.
  4. The System validates the format of the entered data.
  5. The System performs a background check on the data (uniqueness, etc.).
  6. The System creates the account and grants the User access to the platform (limited to non-fully verified features).

### 3. Acceptance Criteria (AC)
**[ ] AC 1:** Successful Registration Given the user provides valid data in all fields;

When the user clicks "Sign Up";

Then the account is created, and the user is redirected to the dashboard with "Level 1" access.

**[ ] AC 2:** Input Format Validation Given the user enters data in an incorrect format (e.g., invalid email or phone number);

When the user attempts to submit the form;

Then the system must display an error message specifically indicating which field contains the error.

**[ ] AC 3:** Duplicate Data Check Given the user enters an Email or Nickname that is already registered in the system;

When the user clicks "Sign Up";

Then the system must prevent registration and display a message stating that the account already exists.

**[ ] AC 4:** Required Fields (Empty State) Given one or more fields are left blank;

When the user clicks "Sign Up";

Then the system must block the submission and highlight the missing fields as mandatory.

## [UC-02] Profile Specialization Setup

**1. Description**

- **Actor:** Performer
    
- **Goal:** To define professional skills and categories to attract relevant job offers.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer navigates to the "My Profile" or "Edit Skills" section.
    
2. The Performer selects one or more categories (e.g., Cleaning, IT, Delivery).
    
3. The Performer adds specific tags or a description of their experience.
    
4. The Performer clicks "Save Changes."
    
5. The System updates the profile and starts suggesting relevant orders in the feed.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Successful Update**
    
    - **Given** the performer has selected at least one valid category;
        
    - **When** they click "Save Changes";
        
    - **Then** the profile is updated, and a "Success" notification is shown.
        
- **[ ] AC 2: Minimum Requirements**
    
    - **Given** the performer tries to save an empty skills list;
        
    - **When** they click "Save Changes";
        
    - **Then** the system prevents the action and prompts the user to select at least one skill.
        
- **[ ] AC 3: Feed Synchronization**
    
    - **Given** the performer has saved new categories;
        
    - **When** they navigate to the "Find Work" tab;
        
    - **Then** the list of orders should be filtered/sorted based on these new categories by default.
        


## [UC-03] Phone Number Verification

**1. Description**

- **Actor:** User (Client or Performer)
    
- **Goal:** To increase account security and trust level by linking a verified phone number.
    

**2. Main Success Scenario (Happy Path)**

1. The User enters their phone number in the Verification section.
    
2. The System sends a 6-digit SMS code to the provided number.
    
3. The User enters the received code into the verification field.
    
4. The System validates the code.
    
5. The System marks the phone number as "Verified."
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Valid Code Entry**
    
    - **Given** the user enters the correct 6-digit code within the time limit;
        
    - **When** they submit;
        
    - **Then** the account status is updated to "Phone Verified."
        
- **[ ] AC 2: Invalid Code Handling**
    
    - **Given** the user enters an incorrect or expired code;
        
    - **When** they submit;
        
    - **Then** the system displays an "Invalid Code" error and allows a retry.
        
- **[ ] AC 3: Resend Cooldown**
    
    - **Given** the user just requested a code;
        
    - **When** they try to click "Resend SMS" immediately;
        
    - **Then** the system blocks the button for 60 seconds to prevent spam.
        


## [UC-04] Portfolio / Work Samples Upload

**1. Description**

- **Actor:** Performer
    
- **Goal:** To showcase previous work results to prove competence to potential clients.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer goes to the "Portfolio" tab.
    
2. The Performer uploads one or multiple images/documents.
    
3. The Performer adds a title and description for each item.
    
4. The System saves the files and displays them on the Performer's public profile.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Image Upload Limits**
    
    - **Given** the user selects a supported file format (JPG/PNG) under the size limit (e.g., 5MB);
        
    - **When** they upload;
        
    - **Then** the image is processed and displayed in the gallery.
        
- **[ ] AC 2: Unsupported File Type**
    
    - **Given** the user tries to upload an unsupported format (e.g., .exe or .zip);
        
    - **When** the file is selected;
        
    - **Then** the system shows an error message and rejects the file.
        
- **[ ] AC 3: Metadata Persistence**
    
    - **Given** the user provides a title and description for a portfolio item;
        
    - **When** the portfolio is saved;
        
    - **Then** the information must be correctly associated and displayed with that specific image.
        


## [UC-05] Client Order History Review

**1. Description**

- **Actor:** Client
    
- **Goal:** To view past activity and reuse previous order templates for efficiency.
    

**2. Main Success Scenario (Happy Path)**

1. The Client navigates to the "My Orders" section.
    
2. The System displays a list of orders categorized by status (Completed, Cancelled, In Progress).
    
3. The Client clicks on a past order to see details.
    
4. The Client clicks "Duplicate" to create a new order based on the old one.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: List Filtering**
    
    - **Given** the client has multiple orders in different states;
        
    - **When** they select the "Completed" filter;
        
    - **Then** only finished jobs are shown in the list.
        
- **[ ] AC 2: Template Duplication**
    
    - **Given** a client chooses a past order;
        
    - **When** they click "Re-post/Duplicate";
        
    - **Then** the system opens a new order form pre-filled with the original title, description, and category.
        


## [UC-06] Role Switching (Dual Profile)

**1. Description**

- **Actor:** User
    
- **Goal:** To switch between "Client" and "Performer" modes without logging out.
    

**2. Main Success Scenario (Happy Path)**

1. The User clicks on the profile menu.
    
2. The User selects the "Switch to Performer" (or Client) toggle.
    
3. The System changes the interface (navigation bar, dashboard widgets) to match the selected role.
    
4. The User continues using the app with the selected role's permissions.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: UI Transformation**
    
    - **Given** the user is currently in "Client" mode;
        
    - **When** they toggle to "Performer";
        
    - **Then** the "Post a Job" button is replaced by "Find Work" or similar performer-centric navigation.
        
- **[ ] AC 2: State Persistence**
    
    - **Given** the user switches roles;
        
    - **When** they refresh the page or restart the app;
        
    - **Then** the system must remember the last active role.
        

## [UC-07] Identity Verification (KYC - Level 2)

**1. Description**

- **Actor:** Performer
    
- **Goal:** To obtain a "Verified" badge and unlock high-budget orders by providing legal ID.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer navigates to "Trust & Verification."
    
2. The Performer uploads a photo of a government-issued ID.
    
3. The Performer takes a "selfie" for face matching.
    
4. The System (or Admin) reviews the documents.
    
5. The System grants "Level 2" status and adds a badge to the profile.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Submission Flow**
    
    - **Given** the user provides all required documents;
        
    - **When** they submit for review;
        
    - **Then** the status changes to "Pending Verification," and the user is notified.
        
- **[ ] AC 2: Rejection Handling**
    
    - **Given** the ID photo is blurry or invalid;
        
    - **When** the admin rejects the verification;
        
    - **Then** the user receives a notification with a specific reason and an option to resubmit.
        


## [UC-08] Notification Preferences

**1. Description**

- **Actor:** User
    
- **Goal:** To control how and when they receive alerts about platform activity.
    

**2. Main Success Scenario (Happy Path)**

1. The User goes to "Settings" -> "Notifications."
    
2. The User toggles specific alerts (e.g., New Messages: ON, Order Updates: ON, Marketing: OFF).
    
3. The User selects the channel (Push, Email, or SMS).
    
4. The System saves the preferences.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Granular Control**
    
    - **Given** the user disables "Email Notifications" for "Marketing";
        
    - **When** a marketing campaign is sent;
        
    - **Then** the user should not receive an email but may still receive Push notifications if enabled.
        
- **[ ] AC 2: Instant Application**
    
    - **Given** a user changes a setting;
        
    - **When** an event occurs immediately after;
        
    - **Then** the system must respect the new settings without requiring a re-login.


## [UC-09] Job Posting (Basic Info)

**1. Description**

- **Actor:** Client
    
- **Goal:** To publish a new job opportunity with essential details to attract performers.
    

**2. Main Success Scenario (Happy Path)**

1. The Client clicks the "Post a Job" button.
    
2. The Client enters a descriptive Title, a detailed Description, and a Budget.
    
3. The Client selects a Category (e.g., Household, Delivery).
    
4. The Client clicks "Publish."
    
5. The System validates the data and makes the post visible in the public feed.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Mandatory Fields** 
    - **Given** the user leaves the Title or Budget empty;
    - **When** they click "Publish";
        
    - **Then** the system highlights the missing fields and prevents submission.
        
- **[ ] AC 2: Budget Formatting** 
    - **Given** the user enters a non-numeric value in the budget field;
    
    - **When** they attempt to submit;
        
    - **Then** the system displays a "Must be a valid number" error.
        
- **[ ] AC 3: Feed Visibility** 
    - **Given** a successful publication;
    
    - **When** any Performer refreshes the feed;
        
    - **Then** the new job appears at the top of the list.
        

---

## [UC-10] Geolocation Tagging

**1. Description**

- **Actor:** Client
    
- **Goal:** To specify the physical location of the task so local performers can find it.
    

**2. Main Success Scenario (Happy Path)**

1. During the job creation process, the Client clicks "Set Location."
    
2. The Client either types an address or selects their current GPS position.
    
3. The System displays the location on a map preview.
    
4. The Client confirms the location.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Address Autocomplete** 
    - **Given** the user starts typing an address;
    
    - **When** they have typed at least 3 characters;
        
    - **Then** the system provides a list of suggested addresses.
        
- **[ ] AC 2: Manual Pin Placement** 
    - **Given** the user is on the map view;
    
    - **When** they click a specific spot on the map;
        
    - **Then** the system updates the coordinates to that specific location.
        

---

## [UC-11] Visual Documentation (Photo Attachments)

**1. Description**

- **Actor:** Client
    
- **Goal:** To provide visual context for the task (e.g., a photo of a broken faucet or a package to be delivered).
    

**2. Main Success Scenario (Happy Path)**

1. The Client clicks "Add Photos" on the job creation screen.
    
2. The Client selects images from their device or takes a new photo via camera.
    
3. The System uploads the files and shows thumbnails.
    
4. The Client publishes the job with the attached photos.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Multiple Uploads** 
    - **Given** a user wants to show different angles;
    
    - **When** they select up to 5 images;
        
    - **Then** the system should handle the bulk upload and display all thumbnails.
        
- **[ ] AC 2: Attachment Removal** 
    - **Given** a user uploaded the wrong photo by mistake;
    
    - **When** they click the "X" on the thumbnail;
        
    - **Then** the file is removed from the draft immediately.
        

---

## [UC-12] Deadline Management

**1. Description**

- **Actor:** Client
    
- **Goal:** To set a time limit for when the task must be completed.
    

**2. Main Success Scenario (Happy Path)**

1. The Client selects a Date and Time using a picker.
    
2. The Client labels the deadline (e.g., "ASAP" or "Scheduled").
    
3. The System displays the "Time Remaining" to potential performers.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Past Date Prevention** 
    - **Given** the user opens the date picker;
    
    - **When** they try to select a date in the past;
        
    - **Then** the system must disable those dates and prevent selection.
        
- **[ ] AC 2: Short-term Warning** 
    - **Given** a user sets a deadline within 1 hour;
    
    - **When** they click save;
        
    - **Then** the system flags the order as "Urgent" in the feed.
        

---

## [UC-13] Pricing Model Selection

**1. Description**

- **Actor:** Client
    
- **Goal:** To choose between a fixed payment or allowing performers to bid their own price.
    

**2. Main Success Scenario (Happy Path)**

1. The Client toggles between "Fixed Price" and "Open for Offers."
    
2. The Client enters a starting price/limit.
    
3. The System adjusts the "Apply" button for performers (either "Accept Price" or "Make a Bid").
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Bidding Range** 
    - **Given** "Open for Offers" is selected;
    
    - **When** the job is published;
        
    - **Then** the UI must clearly show "Negotiable" to the performers.
        

---

## [UC-14] Save Order as Draft

**1. Description**

- **Actor:** Client
    
- **Goal:** To save progress on a complex job description without publishing it immediately.
    

**2. Main Success Scenario (Happy Path)**

1. The Client fills out some fields in the job form.
    
2. The Client clicks "Save as Draft."
    
3. The System stores the information in the "My Drafts" section.
    
4. The Client returns later to finish and publish.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Data Persistence** 
    - **Given** a user has a saved draft;
    
    - **When** they close the app and return;
        
    - **Then** all previously entered text and settings must be restored.
        
- **[ ] AC 2: Draft Expiration** 
    - **Given** a draft hasn't been touched for 30 days;
    
    - **When** the system runs a cleanup;
        
    - **Then** the draft is removed to save storage.
        

---

### [UC-15] Order Cancellation (Pre-selection)

**1. Description**

- **Actor:** Client
    
- **Goal:** To remove a job posting if it's no longer needed, provided no performer has been hired yet.
    

**2. Main Success Scenario (Happy Path)**

1. The Client opens their active job posting.
    
2. The Client clicks "Cancel Order."
    
3. The System asks for a reason (optional).
    
4. The System removes the job from the public feed.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: State Restriction** 
    - **Given** a performer has already been hired;
    
    - **When** the client tries to cancel;
        
    - **Then** the system redirects them to the "Dispute/Cancel Agreement" flow instead of simple deletion.
 
  ### [UC-16] Applicant List Review

**1. Description**

- **Actor:** Client
    
- **Goal:** To compare multiple performers who applied for the job.
    

**2. Main Success Scenario (Happy Path)**

1. The Client views their job posting details.
    
2. The System displays a list of all Performers who clicked "Apply."
    
3. The Client sees each performer's Rating, Badge, and Message.
    
4. The Client clicks on a name to see their full profile.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Sorting Applicants** * **Given** multiple applicants;
    
    - **When** the client selects "Sort by Rating";
        
    - **Then** the performers with the highest scores appear first.
        
- **[ ] AC 2: Counter-offer Visibility** * **Given** an applicant suggested a different price;
    
    - **When** the client views the list;
        
    - **Then** the suggested price must be highlighted next to the performer's name.


### [UC-17] Real-time Job Feed

**1. Description**

- **Actor:** Performer
    
- **Goal:** To see a constantly updated list of available jobs to ensure they don't miss new opportunities.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer opens the "Find Work" section.
    
2. The System fetches the most recent job postings.
    
3. The Performer scrolls through the list.
    
4. The System automatically pushes a "New Jobs Available" notification or updates the list when a new task is published.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Chronological Order**
    
    - **Given** multiple jobs are posted at different times;
        
    - **When** the performer views the feed;
        
    - **Then** the newest jobs must appear at the top.
        
- **[ ] AC 2: Dynamic Refresh**
    
    - **Given** the performer is actively looking at the list;
        
    - **When** a new job is created by a client;
        
    - **Then** the system should display a "New jobs available" banner or inject the job into the feed without a full page reload.
        

---

### [UC-18] Category Filtering

**1. Description**

- **Actor:** Performer
    
- **Goal:** To narrow down the job list to specific industries or types of work they are interested in.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer clicks on the "Filters" icon.
    
2. The Performer selects one or more categories (e.g., "Delivery" and "Cleaning").
    
3. The Performer applies the filters.
    
4. The System displays only the jobs belonging to the selected categories.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Multi-select Support**
    
    - **Given** the performer wants to see both "IT" and "Design" tasks;
        
    - **When** they select both checkboxes;
        
    - **Then** the feed must show results for both categories simultaneously.
        
- **[ ] AC 2: Empty Result State**
    
    - **Given** no jobs exist in a selected category;
        
    - **When** the filter is applied;
        
    - **Then** the system must display a "No jobs found in this category" message with an option to reset filters.
        

---

### [UC-19] Map-based Search

**1. Description**

- **Actor:** Performer
    
- **Goal:** To visualize where jobs are located geographically to plan their route and minimize travel time.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer toggles from "List View" to "Map View."
    
2. The System displays pins on a map representing active job locations.
    
3. The Performer clicks on a pin.
    
4. The System shows a mini-preview of the job (Title, Price, Distance).
    
5. The Performer clicks the preview to open the full job details.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Area-based Loading**
    
    - **Given** the performer pans or zooms the map;
        
    - **When** the map movement stops;
        
    - **Then** the system should fetch and display pins only for the currently visible area.
        
- **[ ] AC 2: User Location Centering**
    
    - **Given** the performer grants GPS permissions;
        
    - **When** they click the "My Location" button;
        
    - **Then** the map must center on their current coordinates and show nearby pins.
        

---

### [UC-20] Price Range Filtering

**1. Description**

- **Actor:** Performer
    
- **Goal:** To exclude low-paying jobs and focus on tasks that meet their minimum income requirements.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer opens the filter menu.
    
2. The Performer enters a "Minimum Price" value.
    
3. The Performer applies the filter.
    
4. The System refreshes the feed to show only jobs with a budget equal to or higher than the specified amount.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Value Validation**
    
    - **Given** the performer enters a negative number or a maximum price lower than the minimum;
        
    - **When** they try to apply;
        
    - **Then** the system must block the action and show a validation error.
        
- **[ ] AC 2: Live Count**
    
    - **Given** the performer adjusts the price slider;
        
    - **When** the slider moves;
        
    - **Then** the system should (ideally) show the number of matching results in real-time on the "Apply" button.
        

---

### [UC-21] Favorites / Bookmarks

**1. Description**

- **Actor:** Performer
    
- **Goal:** To save interesting jobs to a dedicated list so they can review or apply to them later.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer sees an interesting job in the feed.
    
2. The Performer clicks the "Heart" or "Bookmark" icon on the job card.
    
3. The System adds the job to the "My Favorites" section.
    
4. The Performer navigates to "My Favorites" to view all saved tasks.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Toggle State**
    
    - **Given** a job is already in favorites;
        
    - **When** the performer clicks the icon again;
        
    - **Then** the job must be removed from favorites and the icon visual state updated.
        
- **[ ] AC 2: Availability Check**
    
    - **Given** a bookmarked job is deleted or filled by another performer;
        
    - **When** the performer views their favorites list;
        
    - **Then** the job should be marked as "Unavailable" or "Expired."
        

---

### [UC-22] Client Exclusion (Hidden Feed)

**1. Description**

- **Actor:** Performer
    
- **Goal:** To hide jobs from specific clients with whom they do not wish to work.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer views a job post from a specific Client.
    
2. The Performer selects "Don't show jobs from this user" in the options menu.
    
3. The System removes all current posts from that client from the performer's feed.
    
4. The System ensures future posts from this client are automatically hidden for this performer.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Immediate Removal**
    
    - **Given** the performer blocks a client;
        
    - **When** the action is confirmed;
        
    - **Then** the feed should update instantly without a page refresh.
        
- **[ ] AC 2: Blacklist Management**
    
    - **Given** a performer has blocked multiple clients;
        
    - **When** they go to "Settings -> Blocked Users";
        
    - **Then** they should be able to see the list and unblock a client if desired.
        

---

### [UC-23] Proximity Visibility

**1. Description**

- **Actor:** Performer
    
- **Goal:** To quickly see how far away a job is from their current location without opening a map.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer views the standard job feed.
    
2. The System calculates the distance between the Performer's current GPS location and the job's location.
    
3. The System displays "X km away" directly on each job card in the list.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Distance Accuracy**
    
    - **Given** the performer's location is known;
        
    - **When** a job is 5.2 km away;
        
    - **Then** the label should reflect this distance rounded to one decimal place.
        
- **[ ] AC 2: Permission Fallback**
    
    - **Given** the performer has disabled GPS;
        
    - **When** they view the feed;
        
    - **Then** the distance label should be hidden or replaced with the name of the neighborhood/city.
        

---

### [UC-24] Category-Specific Push Notifications

**1. Description**

- **Actor:** Performer
    
- **Goal:** To be notified instantly when a job in their preferred category is posted, even when the app is closed.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer subscribes to notifications for the "Plumbing" category.
    
2. A Client publishes a new "Plumbing" task.
    
3. The System identifies all performers subscribed to this category.
    
4. The System sends a Push Notification to the Performer's device.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Instant Delivery**
    
    - **Given** the performer has a stable internet connection;
        
    - **When** the job is published;
        
    - **Then** the notification should arrive within seconds.
        
- **[ ] AC 2: Category Relevance**
    
    - **Given** the performer is only subscribed to "IT";
        
    - **When** a "Cleaning" job is posted;
        
    - **Then** the performer should **not** receive a notification.


### [UC-25] Job Application with Cover Letter

**1. Description**

- **Actor:** Performer
    
- **Goal:** To apply for a specific task and explain why they are the best fit for the job.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer views the details of an active job posting.
    
2. The Performer clicks the "Apply" button.
    
3. The Performer enters a short message (Cover Letter) describing their experience or plan.
    
4. The Performer submits the application.
    
5. The System adds the Performer to the Client's applicant list and notifies the Client.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Application Submission**
    
    - **Given** the performer has entered a valid cover letter;
        
    - **When** they click "Submit Application";
        
    - **Then** the application is saved, and a success message is displayed.
        
- **[ ] AC 2: Message Length Validation**
    
    - **Given** the user tries to submit an empty message or one exceeding 500 characters;
        
    - **When** they click submit;
        
    - **Then** the system displays a validation error and blocks the request.
        
- **[ ] AC 3: Duplicate Prevention**
    
    - **Given** the performer has already applied to this job;
        
    - **When** they view the job details again;
        
    - **Then** the "Apply" button is disabled and replaced with "Already Applied."
        

---

### [UC-26] Price Counter-Offer (Bidding)

**1. Description**

- **Actor:** Performer
    
- **Goal:** To propose a different price if the client's budget does not match the performer's expectations.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer clicks "Apply" on a job with "Open for Offers" status.
    
2. The Performer enters their proposed price.
    
3. The Performer submits the application.
    
4. The System displays this price specifically to the Client in the applicant list.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Offer Visibility**
    
    - **Given** the performer submitted a bid of $50 on a $40 job;
        
    - **When** the client views applicants;
        
    - **Then** the client must clearly see the $50 counter-offer.
        
- **[ ] AC 2: Reasonable Range Validation**
    
    - **Given** the performer enters a price of 0 or a negative number;
        
    - **When** they click submit;
        
    - **Then** the system must block the offer and prompt for a positive value.
        

---

### [UC-27] Performer Profile Review

**1. Description**

- **Actor:** Client
    
- **Goal:** To evaluate the quality of an applicant based on their platform history.
    

**2. Main Success Scenario (Happy Path)**

1. The Client opens the list of applicants for their job.
    
2. The Client clicks on a Performer’s name/avatar.
    
3. The System opens a modal or page showing the Performer's average rating, total completed tasks, and individual reviews from past clients.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Summary Statistics**
    
    - **Given** the performer has completed 10 jobs with varying ratings;
        
    - **When** the client views the profile;
        
    - **Then** the system must display the calculated average star rating and total job count.
        
- **[ ] AC 2: Review Access**
    
    - **Given** the performer has past feedback;
        
    - **When** the client scrolls down;
        
    - **Then** they must be able to read the specific comments left by previous clients.
        

---

### [UC-28] Pre-Hire Messaging

**1. Description**

- **Actor:** Client
    
- **Goal:** To discuss details and clarify expectations with a candidate before officially hiring them.
    

**2. Main Success Scenario (Happy Path)**

1. The Client views an applicant in the list.
    
2. The Client clicks the "Message" icon.
    
3. The System opens a chat window linked to this specific job.
    
4. The Client sends a question; the Performer receives a notification and responds.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Contextual Chat**
    
    - **Given** the client starts a chat from a job application;
        
    - **When** the chat opens;
        
    - **Then** the top of the chat should display the job title as the current context.
        
- **[ ] AC 2: Instant Notification**
    
    - **Given** the client sends a message;
        
    - **When** the performer is online;
        
    - **Then** the performer must receive a real-time notification (WebSocket or Push).
        

---

### [UC-29] Hire Confirmation

**1. Description**

- **Actor:** Client
    
- **Goal:** To officially select a Performer and start the job contract.
    

**2. Main Success Scenario (Happy Path)**

1. The Client decides on a Performer and clicks the "Hire" button.
    
2. The System prompts for a final confirmation.
    
3. The Client confirms.
    
4. The System changes the job status to "In Progress" and notifies the hired Performer.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Selection finalization**
    
    - **Given** the client clicks "Hire";
        
    - **When** they confirm the action;
        
    - **Then** all other applicants should receive a notification that the position has been filled.
        
- **[ ] AC 2: Job Status Update**
    
    - **Given** a performer is hired;
        
    - **When** the operation completes;
        
    - **Then** the job must be removed from the public "Find Work" feed.
        

---

### [UC-30] Hiring Confirmation Receipt

**1. Description**

- **Actor:** Performer
    
- **Goal:** To receive formal notice that their application was accepted and they can begin work.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer receives a push notification: "You've been hired for [Job Title]!"
    
2. The Performer clicks the notification.
    
3. The System redirects them to the "Active Jobs" tab with the specific order details open.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Direct Redirection**
    
    - **Given** the performer is on any screen in the app;
        
    - **When** they tap the hiring notification;
        
    - **Then** the system must navigate directly to the specific active job view.


### [UC-31] Withdraw Application

**1. Description**

- **Actor:** Performer
    
- **Goal:** To cancel an application if they are no longer available or interested.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer goes to their "Applications" list.
    
2. The Performer clicks "Withdraw" on a pending application.
    
3. The System asks for confirmation.
    
4. The System removes the application and deletes the entry from the Client's applicant list.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Removal from Client View**
    
    - **Given** the performer withdraws;
        
    - **When** the client refreshes their applicant list;
        
    - **Then** that performer's entry must no longer be visible.
        
- **[ ] AC 2: Hire State Restriction**
    
    - **Given** the client has already clicked "Hire" (status is In Progress);
        
    - **When** the performer tries to withdraw;
        
    - **Then** the button should be disabled (must use "Cancel Order" flow instead).
        

---

### [UC-32] Real-time Status: "Heading There"

**1. Description**

- **Actor:** Performer / Client
    
- **Goal:** To inform the client that the performer has started traveling to the job site.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer opens the active job.
    
2. The Performer clicks "On my way."
    
3. The System updates the status for the Client.
    
4. The Client sees an "In Transit" status and an estimated time of arrival (if GPS is enabled).
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Visual Indicator**
    
    - **Given** the performer clicks "On my way";
        
    - **When** the client views the job;
        
    - **Then** a status badge "Performer is En Route" must be visible.
        
- **[ ] AC 2: Timestamp Logging**
    
    - **Given** the status change occurs;
        
    - **When** the system saves the update;
        
    - **Then** it must log the exact time the travel started for dispute resolution purposes.


### [UC-33] Secure In-App Messaging

**1. Description**

- **Actor:** User (Client or Performer)
    
- **Goal:** To communicate safely within the platform without sharing personal phone numbers or messengers.
    

**2. Main Success Scenario (Happy Path)**

1. The User opens an active order.
    
2. The User clicks "Open Chat."
    
3. The User types a message and clicks "Send."
    
4. The System delivers the message instantly to the recipient.
    
5. The System stores the chat history for future reference or dispute resolution.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Real-time Delivery**
    
    - **Given** both users are online;
        
    - **When** a message is sent;
        
    - **Then** it must appear in the recipient's chat window within 1 second.
        
- **[ ] AC 2: Privacy Protection**
    
    - **Given** the chat is active;
        
    - **When** a user tries to find the other's phone number or email;
        
    - **Then** the system must keep that data hidden unless a user explicitly shares it in text.
        
- **[ ] AC 3: Attachment Support**
    
    - **Given** the user is in the chat;
        
    - **When** they click the "Paperclip" icon;
        
    - **Then** they must be able to select and send a file or image from their device.
        

---

### [UC-34] Progress Photo Documentation

**1. Description**

- **Actor:** Performer
    
- **Goal:** To send photos of the work-in-progress or the final result to the client for transparency.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer opens the job chat or "Active Order" screen.
    
2. The Performer takes a photo of the completed task.
    
3. The Performer adds a caption (e.g., "Faucet fixed").
    
4. The System uploads the photo and notifies the Client.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Proof of Work**
    
    - **Given** the performer is at the location;
        
    - **When** they upload a photo through the app;
        
    - **Then** the system should automatically tag the photo with a timestamp.
        
- **[ ] AC 2: Resolution Optimization**
    
    - **Given** the user uploads a high-res photo;
        
    - **When** the system processes it;
        
    - **Then** it should be compressed to save mobile data while maintaining legible quality.
        

---

### [UC-35] "Work Started" Trigger

**1. Description**

- **Actor:** Performer
    
- **Goal:** To formally signal that they have arrived and are beginning the task.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer arrives at the job site.
    
2. The Performer clicks "Start Working."
    
3. The System records the start time.
    
4. The System updates the status for the Client to "In Progress."
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Proximity Check**
    
    - **Given** the job has a specific location;
        
    - **When** the performer clicks "Start Working" but is more than 500m away;
        
    - **Then** the system should prompt "Are you sure you are at the location?".
        
- **[ ] AC 2: Client Notification**
    
    - **Given** the status changes;
        
    - **When** the system updates;
        
    - **Then** the client must receive a push notification: "[Performer] has started the task."
        

---

### [UC-36] "Task Completed" Declaration

**1. Description**

- **Actor:** Performer
    
- **Goal:** To notify the client that the work is finished and they are ready to be paid.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer finishes the work.
    
2. The Performer clicks "Mark as Completed."
    
3. The System prompts the performer to attach a final result photo.
    
4. The System changes the status to "Pending Client Approval."
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Final Step Requirement**
    
    - **Given** the performer clicks "Completed";
        
    - **When** they have not attached a required photo (if specified by the client);
        
    - **Then** the system should remind them to add a photo before finalizing.
        

---

### [UC-37] Job Approval (Closure)

**1. Description**

- **Actor:** Client
    
- **Goal:** To confirm they are satisfied with the result and officially close the order.
    

**2. Main Success Scenario (Happy Path)**

1. The Client receives a "Task Completed" notification.
    
2. The Client inspects the work (or the uploaded proof).
    
3. The Client clicks "Confirm & Release Payment."
    
4. The System changes the status to "Completed" and triggers the payment release.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Irreversibility**
    
    - **Given** the client clicks "Confirm";
        
    - **When** the action is saved;
        
    - **Then** the order cannot be moved back to "In Progress" without support intervention.
        

---

### [UC-38] Revision Request (Rework)

**1. Description**

- **Actor:** Client
    
- **Goal:** To ask the performer to fix specific issues before the payment is released.
    

**2. Main Success Scenario (Happy Path)**

1. The Client reviews the "Completed" task but finds an issue.
    
2. The Client clicks "Request Revision."
    
3. The Client types what needs to be fixed.
    
4. The System puts the job back into "In Progress" and notifies the Performer.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Specificity Requirement**
    
    - **Given** the client selects "Revision";
        
    - **When** they try to submit without a comment;
        
    - **Then** the system blocks the action and asks for a description of the required changes.
        
- **[ ] AC 2: Status Visibility**
    
    - **Given** a revision is requested;
        
    - **When** the performer views the job;
        
    - **Then** the status must be highlighted as "Needs Attention" or "Rework Requested."
        

---

### [UC-39] Message Read Receipts

**1. Description**

- **Actor:** User
    
- **Goal:** To know if their message has been seen by the other party to manage expectations.
    

**2. Main Success Scenario (Happy Path)**

1. User A sends a message to User B.
    
2. User B opens the chat and views the message.
    
3. The System updates the status of the message to "Read" (e.g., double checkmarks).
    
4. User A sees the "Read" indicator.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Visual Feedback**
    
    - **Given** a message is delivered but not opened;
        
    - **When** the sender views the chat;
        
    - **Then** the system shows a "Delivered" icon.
        
- **[ ] AC 2: State Synchronization**
    
    - **Given** User B opens the app on a different device (laptop vs mobile);
        
    - **When** they read the message;
        
    - **Then** the status must update across all platforms for the sender.
        

---

### [UC-40] No-Response Alert (Inactivity)

**1. Description**

- **Actor:** System
    
- **Goal:** To detect when a performer or client is ignoring messages during an active order and escalate the issue.
    

**2. Main Success Scenario (Happy Path)**

1. A message is sent by the Client during an "In Progress" job.
    
2. The System detects that the Performer hasn't opened the chat for 4 hours.
    
3. The System sends a reminder push notification to the Performer.
    
4. The System notifies the Client that they can contact support if the delay continues.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Automatic Trigger**
    
    - **Given** the 4-hour window has passed without activity;
        
    - **When** the system background worker runs;
        
    - **Then** a "Gentle Reminder" notification is sent to the inactive party.
        
- **[ ] AC 2: Escalation Path**
    
    - **Given** inactivity lasts for 12 hours;
        
    - **When** the system detects this;
        
    - **Then** a "Report Issue" button must be prominently displayed to the active party.


### [UC-41] Payment Method Integration

**1. Description**

- **Actor:** Client
    
- **Goal:** To securely link a credit/debit card to the account for seamless job payments.
    

**2. Main Success Scenario (Happy Path)**

1. The Client navigates to "Wallet" -> "Add Payment Method."
    
2. The Client enters card details (Number, Expiry, CVV).
    
3. The System performs a test transaction (e.g., $0.00 or $1.00 authorization) via a payment gateway.
    
4. The System saves a secure token representing the card (not the actual card number).
    
5. The Client sees the card in their list of payment methods.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Successful Tokenization**
    
    - **Given** the card details are valid and pass the 3D-Secure check;
        
    - **When** the user clicks "Save Card";
        
    - **Then** the system must store a payment token and display the last 4 digits of the card.
        
- **[ ] AC 2: Invalid Card Handling**
    
    - **Given** an expired card or incorrect CVV;
        
    - **When** the authorization fails;
        
    - **Then** the system must display the specific error from the payment provider and not save the card.
        

---

### [UC-42] Escrow Fund Reservation (Secure Deal)

**1. Description**

- **Actor:** System / Client
    
- **Goal:** To "freeze" the job funds on the Client's card when a Performer is hired, ensuring the money is available for the Performer upon completion.
    

**2. Main Success Scenario (Happy Path)**

1. The Client clicks "Hire" on a specific Performer.
    
2. The System calculates the Total (Price + Service Fee).
    
3. The System requests a "Hold" from the payment gateway.
    
4. The System notifies the Performer that the funds are secured.
    
5. The job status moves to "In Progress."
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Insufficient Funds**
    
    - **Given** the Client's card is declined due to a lack of funds;
        
    - **When** the "Hire" action is triggered;
        
    - **Then** the system must block the hiring process and prompt the Client to use a different card.
        
- **[ ] AC 2: State Persistence**
    
    - **Given** the funds are on hold;
        
    - **When** the job is active;
        
    - **Then** neither the Client nor the Performer can access the money until the job is "Completed" or "Cancelled."
        

---

### [UC-43] Performer Wallet Balance

**1. Description**

- **Actor:** Performer
    
- **Goal:** To track total earnings, pending payments, and available funds for withdrawal.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer navigates to the "Wallet" or "Earnings" section.
    
2. The System displays three balances: "Pending" (In-progress jobs), "Cleared" (Completed, waiting for payout), and "Total Earned."
    
3. The Performer views a summary of recent earnings.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Real-time Update**
    
    - **Given** a Client approves a job;
        
    - **When** the Performer opens the Wallet;
        
    - **Then** the amount must move from "Pending" to "Cleared" immediately.
        
- **[ ] AC 2: Currency Consistency**
    
    - **Given** the platform operates in a specific region;
        
    - **When** the wallet is displayed;
        
    - **Then** all amounts must be formatted according to the local currency (e.g., $ or â¬) and locale.
        

---

### [UC-44] Payout Request (Withdrawal)

**1. Description**

- **Actor:** Performer
    
- **Goal:** To transfer cleared earnings from the platform wallet to a personal bank account.
    

**2. Main Success Scenario (Happy Path)**

1. The Performer clicks "Withdraw Funds."
    
2. The Performer enters the amount and selects a saved bank account.
    
3. The System validates that the Performer has enough "Cleared" funds.
    
4. The System initiates the transfer and updates the Wallet balance.
    
5. The Performer receives a "Withdrawal Initiated" email.
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Minimum Withdrawal Limit**
    
    - **Given** the user tries to withdraw $2 while the minimum is $10;
        
    - **When** they click "Withdraw";
        
    - **Then** the system must block the action and show the minimum requirement.
        
- **[ ] AC 2: Fraud Check Delay**
    
    - **Given** a large withdrawal request;
        
    - **When** the request is submitted;
        
    - **Then** the system should flag it for "Admin Review" and set the status to "Pending Review" instead of "Processed."
        

---

### [UC-45] Transaction History and Receipts

**1. Description**

- **Actor:** User
    
- **Goal:** To have a clear, auditable record of all financial activity on the platform.
    

**2. Main Success Scenario (Happy Path)**

1. The User opens "Transaction History."
    
2. The System displays a list of all payments, holds, and withdrawals.
    
3. The User clicks on a specific entry.
    
4. The System provides a detailed breakdown (Job ID, Date, Amount, Fees, Tax).
    
5. The User clicks "Download PDF Receipt."
    

**3. Acceptance Criteria (AC)**

- **[ ] AC 1: Search and Filter**
    
    - **Given** a user has hundreds of transactions;
        
    - **When** they filter by "Date Range";
        
    - **Then** the list should update to show only the relevant entries.
        
- **[ ] AC 2: Accurate Fee Breakdown**
    
    - **Given** a job payment;
        
    - **When** viewing the receipt;
        
    - **Then** it must clearly separate the Job Price from the Platform Service Fee.
