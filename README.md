# n8n Workflow Backup

## Overview

This n8n workflow automates the task of backing up your n8n workflows and security audit data to Google Drive. It creates a backup system that runs on a schedule, organizing your backups by date and providing both workflow JSONs and security audit reports.

## Features

- **Scheduled Backups**: Automatically runs at a configurable time (default: 1:30 AM)
- **Date-Based Organization**: Creates dated folders in Google Drive for easy retrieval
- **Workflow Backup**: Exports all workflows from your n8n instance as JSON files
- **Security Audit**: Generates a security audit report of your n8n instance
- **Markdown Conversion**: Transforms security audit data into readable Markdown format
- **Structured Storage**: Organizes backups in a hierarchical folder structure

## How It Works

The workflow is divided into three main sections:

### 1. Setup and Folder Creation
- A schedule trigger initiates the workflow at the specified time
- The current date and time are captured
- A new folder is created in Google Drive with the current date as its name

### 2. Security Audit Export
- Inside the date folder, a subfolder named "audit" is created
- The n8n security audit is generated
- The audit data (in JSON format) is converted to a well-formatted Markdown document
- The Markdown document is saved to the audit folder in Google Drive

### 3. Workflow Export
- All workflows are retrieved from your n8n instance
- Each workflow's JSON data is converted to binary format
- The workflows are saved as individual JSON files in the date folder

## Requirements

- n8n instance with API access
- Google Drive account with OAuth2 authentication
- Proper credentials setup in n8n

## Setup Instructions

1. Import the workflow JSON into your n8n instance
2. Configure Google Drive credentials
3. Set up n8n API credentials
4. Modify the Google Drive folder ID to match your desired backup location
5. Adjust the schedule trigger time as needed

## Customization

You can customize this workflow by:
- Changing the backup frequency in the Schedule Trigger node
- Modifying the folder structure in Google Drive
- Expanding the workflow to include additional backup types
- Adding notification nodes (e.g., Slack, Email) to alert upon completion

## Credits

This workflow is modified from the template created by Phil ([https://n8n.io/workflows/3112-backup-n8n-workflows-to-google-drive/](https://n8n.io/workflows/3112-backup-n8n-workflows-to-google-drive/)) with additional features added.

## License

This workflow is provided under the same license as n8n. Feel free to modify and share it according to your needs.

---

*Ensure you have the correct permissions for your Google Drive account and n8n instance before implementing this workflow.*
