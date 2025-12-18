Asset Checkout – ServiceNow Custom Application

This repository contains a ServiceNow Update Set XML for Asset Checkout functionality that implements a simple, clean, and functional asset checkout process inside your ServiceNow instance.

This update set showcase a complete working example with scripts, form logic, validations, and user guidance.

The goal of this update set is to solve one core problem:

How can users check out and return assets safely while ensuring availability is updated automatically?

This update set provides:

✔ A custom Asset Checkout form

✔ Automatic availability handling

✔ Real-time client-side checks

✔ Mandatory field enforcement

✔ Business rules to prevent invalid checkouts

✔ Custom fields required for tracking asset state

It is designed to be lightweight, simple, and easy to modify.

🟢 Table & Field Updates


Custom table: u_asset_checkout_2 is used to Request/Check-out asset

Custom table: u_asset_items is base table which contains Asset data

🟢 Approvals - "Asset Request Approval"

Purpose: Makes asset request process more controlled

What it does:
when user requests an asset it sends an approval this prevents users from requesting irrelevent asset requests

🟢 Client Script – “Asset info”

Purpose:
Shows helpful messages to the user about the selected asset when they open the form.

What it does:

When the form loads, it reads details (through g_scratchpad) such as
Asset name,
Category,
Condition,
Status.

Displays these values as subtle form messages so the user immediately understands what they are checking out.

Why it matters:
This improves user experience

🟢 UI Policy – “Request Stage Mandatory fields”

Purpose:
Ensures important fields become mandatory when a user is checking out an asset.

What it does:

Applies conditions when certain fields (like checkout/return status) are empty

Forces key fields to become mandatory

Automatically reverses when conditions are no longer met

Why it matters:
Prevents bad data, incomplete requests, and invalid form submissions.

🟢 Business Rule – “Asset availability”

Purpose:
Controls backend logic that validates and updates asset availability.

Runs:
Before Insert/Update

What it handles:

✔ If a user attempts to check out an asset:

✔ It checks availability

✔ Prevents checkout if the asset is already unavailable

✔ If unavailable → marks the asset as "unavailable"

✔ If a user returns an asset:
Automatically flips the asset back to "available"

Why it matters:
This guarantees clean workflow logic.
No asset will ever be double-checked-out.

📌 This update set was created as a learning project.

It demonstrates practical use of:

Business Rules

Client Scripts

UI Policies

Custom Tables

Update Set Migration

Asset lifecycle logic



