# Zapier Payment Follow-up Agent

An AI-powered payment follow-up and tracking agent built using Zapier Agents, Google Sheets, and Gmail.

The agent automates payment reminders, processes payment confirmation emails, extracts transaction IDs, and updates payment records in Google Sheets.

---

## Agent Overview

The Zapier Agent contains instructions for processing payment confirmations, identifying spreadsheet records, and safely updating payment information.

## Project Overview

Manually tracking pending payments and updating payment records can be repetitive and error-prone.

This project automates the payment follow-up process using a Zapier AI Agent.

The agent can:

- Identify users with pending payments
- Send payment reminder emails automatically
- Process payment confirmation replies
- Extract transaction IDs from emails
- Match the sender with the correct Google Sheets record
- Update payment status from `Pending` to `Completed`
- Store the transaction ID in Google Sheets
- Handle missing transaction IDs before updating records

---

## Workflow

The automation follows two main workflows.

## Payment Reminder

```text
Google Sheets
      |
      v
Check Payment Status
      |
      v
Status = Pending?
      |
     Yes
      |
      v
Send Reminder via Gmail
      |
      v
Update Reminder Sent = Yes


### Payment Confirmation
Customer Replies to Email
          |
          v
     Gmail Reply
          |
          v
Agent Detects Payment Confirmation
          |
          v
Extract Transaction ID
          |
          v
Get Sender Email Address
          |
          v
Lookup Email in Google Sheets
          |
          v
Get Matching Row Number
          |
          v
Update Spreadsheet Row
          |
     +----+----+
     |         |
     v         v
 Completed   Transaction ID

## Tech Stack
| Technology            | Purpose                                               |
| --------------------- | ----------------------------------------------------- |
| Zapier Agents         | AI agent and workflow orchestration                   |
| Google Sheets         | Payment database and status tracking                  |
| Gmail                 | Sending reminders and receiving payment confirmations |
| AI Agent Instructions | Understanding emails and controlling workflow logic   |
| GitHub                | Project documentation and version tracking            |


Google Sheet Structure (Dummy Data)
| Name         | Email                                         | Payment Status | Transaction ID | Reminder Sent |
| ------------ | --------------------------------------------- | -------------- | -------------- | ------------- |
| Aarav Sharma | [aarav@example.com](mailto:aarav@example.com) | Pending        | -              | No            |
| Priya Mehta  | [priya@example.com](mailto:priya@example.com) | Completed      | TXN784512963   | Yes           |
| Rohan Verma  | [rohan@example.com](mailto:rohan@example.com) | Pending        | -              | No            |

## Agent Tools
The Zapier Agent uses the following tools:

Gmail: Send Email
Gmail: Find Email
Gmail: Reply to Email
Google Sheets: Lookup Spreadsheet Rows (Advanced)
Google Sheets: Update Spreadsheet Row(s)

Google Sheets is also connected as a knowledge source for the agent.

## Agent Logic

When a payment confirmation email is received, the agent:

Reads the incoming email.
Identifies whether the sender has confirmed payment.
Extracts the transaction ID.
Retrieves the sender's email address.
Searches the Google Sheet using the sender's email.
Retrieves the corresponding spreadsheet row number.
Updates the payment status to Completed.
Stores the extracted transaction ID in the same row.

The agent always performs the spreadsheet lookup before attempting to update a row.

## Project Status

Working Prototype

The complete workflow has been successfully tested:

Pending Payment → Email Reminder → Payment Confirmation → Transaction ID Extraction → Spreadsheet Lookup → Payment Status Updated


Author
Mehak Chhabra



