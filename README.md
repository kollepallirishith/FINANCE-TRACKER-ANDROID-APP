# Money Tracker Android App

## Overview
The **Money Tracker** app helps users manage and track their financial transactions by extracting SMS data related to spending, deposits, and balance updates. It provides a user-friendly interface to visualize transaction details, set monthly limits, and view graphical data related to expenses. The app features functionality for permission management, transaction parsing, and real-time data updating.

## Features
- **Transaction Tracking**: Automatically fetches and parses SMS data for transactions related to spending, deposits, and balance updates.
- **Monthly Limit**: Allows users to set and track their monthly expenditure limit.
- **Graphical Analysis**: Displays a line chart showing daily spending trends.
- **Real-Time Updates**: Refreshes transaction data and updates UI elements like the total spent and current balance.
- **Settings**: Users can adjust app settings, including the monthly limit.

## Permissions
- **SMS Permission**: The app requires access to read SMS messages to fetch transaction details.
  
  When first launched, the app asks for **READ_SMS** permission. The user must grant this permission to fetch transaction data.

## Installation

1. Clone or download the repository.
2. Open the project in **Android Studio**.
3. Ensure you have the necessary permissions set in the `AndroidManifest.xml`:
   ```xml
   <uses-permission android:name="android.permission.READ_SMS"/>
   ```

4. Build and run the app on your Android device.

## Screenshots
- **Main Activity**: Displays transaction list and summary.
- **Graph Popup**: Shows spending data on a line chart.
- **Settings**: Allows users to set monthly limits.

## Components
1. **MainActivity**:
   - Displays transaction data using a RecyclerView.
   - Allows users to refresh data, view spending statistics, and navigate to the settings page.
   - Features a progress bar to show the percentage of the monthly limit used.

2. **Transaction Adapter**:
   - Binds the list of transactions to the RecyclerView for display.

3. **Graph Popup**:
   - Shows a line chart of spending by date.
   - Allows users to filter spending data by specific dates using a date picker.

4. **SettingsActivity**:
   - Provides a UI for users to adjust their monthly spending limit.

5. **Permissions Handling**:
   - Ensures the app has the necessary permissions to read SMS and fetch transaction data.

## Code Structure

- **MainActivity**:
  - Initializes UI elements, manages transactions, and updates the progress bar based on spending.
  
- **TransactionAdapter**:
  - A custom RecyclerView adapter that binds transaction data to the list.

- **Transaction Model**:
  - Defines the structure of a transaction, including the amount, type (Spent, Deposited, Credited), date, and transaction details.

- **SMS Data Parsing**:
  - Extracts transaction data from SMS messages using regular expressions for "Spent," "Deposited," and "Credited" transaction types.

- **Graph Visualization**:
  - Uses MPAndroidChart to display a line chart of daily spending.

## Usage

### Transaction Refresh
1. Click the **Refresh** button to fetch new transaction data from SMS.
2. The app updates the **Total Spent** and **Current Balance** displayed on the main screen.

### Setting Monthly Limit
1. Navigate to the **Settings** screen by clicking the **Settings** button.
2. Set your desired **Monthly Limit**.
3. The app will automatically update the progress bar to reflect spending against the set limit.

### Viewing Graph
1. Click the **Show Graph** button to view a graph of your spending.
2. The graph displays daily spending trends, and you can filter by date using the **Select Date** button.

   ###note : works currently only for bank of baroda you can change the regex logic for your bank
   


