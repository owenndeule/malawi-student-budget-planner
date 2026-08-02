# 🇲🇼 Malawi Student Budget Planner

A fully interactive, offline-first budget management web application designed specifically for university students in Malawi. Track your income, plan your expenses, record daily transactions, and monitor your savings—all in one place.

![Budget Planner Screenshot](https://via.placeholder.com/800x400.png?text=Malawi+Student+Budget+Planner)

## 📋 Table of Contents
- [Features](#-features)
- [Live Demo](#-live-demo)
- [Getting Started](#-getting-started)
- [Usage Guide](#-usage-guide)
- [Technologies Used](#-technologies-used)
- [Project Structure](#-project-structure)
- [How It Works](#-how-it-works)
- [Responsive Design](#-responsive-design)
- [Contributing](#-contributing)
- [Roadmap](#-roadmap)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## ✨ Features

### 💰 Income Tracking
- Enter income from multiple sources: Allowance, Part-time Job, and Other Income
- Real-time total income calculation as you type
- Auto-saves to your browser's local storage

### 📋 Expense Planner (Checklist)
- 10 pre-defined expense categories: Food, Transport, Rent, Tuition, Books, Entertainment, Utilities, Health, Clothing, Other
- Custom "Other" category with user-defined labels
- Check/uncheck categories to activate/deactivate them
- Enter planned amounts for each active category
- **Save Planned Expenses** button to persist your budget to localStorage

### 📝 Expenditure Recorder
- Log daily transactions with date, category, description, and amount
- Custom category support with "Other" option and custom label input
- Delete individual transactions with one click
- Transactions are stored locally and persist across sessions

### 📊 Summary Dashboard
- **Total Income** – your combined earnings from all sources
- **Planned Expenses** – your budgeted spending from the checklist
- **Actual Expenses** – what you've recorded in transactions
- **Budget Surplus** – income minus planned expenses (shows if you're within budget)
- **Actual Savings** – income minus actual spending (your real savings)
- **Progress Bar** – visual comparison of actual vs planned spending (0–100%)
- **Spending Trend** – "✅ On Track" or "❌ Over Budget" indicator

### 🚨 Budget Alerts
- Visual warning banner appears when actual spending exceeds planned budget
- Shows the exact amount you've overspent
- Auto-dismisses when spending is back within budget

### 📊 Spending Breakdown Chart
- Interactive pie chart showing spending by category
- Color-coded legend with amounts and percentages
- Updates automatically as you add or delete transactions
- Displays "No data" message when no transactions exist

### 💾 Data Management
- **Auto-save** – all data is automatically saved to your browser's local storage
- **Export JSON** – full backup of all budget data (income, expenses, transactions)
- **Export CSV** – transaction history for spreadsheet analysis (Excel, Google Sheets)
- **Import JSON** – restore from a previous backup file
- **Clear Month** – reset all data for a fresh start (with confirmation modal)

### 🌙 User Experience
- Clean, modern interface with smooth animations
- Toast notifications for all actions (save, delete, export, import)
- Confirmation modal for destructive actions (Clear Month)
- Keyboard shortcut: `ESC` to close modal dialogs

---

## 🚀 Live Demo

You can try the application instantly by opening the `index.html` file in any modern web browser. No server setup required!

**Demo Data**: The app comes with a clean state. Add your own income, plan expenses, and record transactions to see it come to life.

---

## 🛠️ Getting Started

### Prerequisites
- Any modern web browser (Chrome 90+, Firefox 88+, Edge 90+, Safari 14+)
- No internet connection required after initial load
- JavaScript enabled

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/malawi-student-budget-planner.git
   cd malawi-student-budget-planner
   ```

2. **Open the application**
   Simply open the `index.html` file in your browser:
   ```bash
   # On macOS
   open index.html

   # On Windows
   start index.html

   # On Linux
   xdg-open index.html
   ```

3. **Start budgeting!**
   - Enter your income sources
   - Check the expense categories you want to track
   - Enter planned amounts and click "Save Planned Expenses"
   - Record your daily transactions using the Expenditure Recorder
   - Monitor your progress in the Summary dashboard

### Running with Live Server (Optional)
For a better development experience with auto-reload:

```bash
# Using Python's built-in server
python3 -m http.server 8000

# Using npx (Node.js)
npx serve .

# Using VS Code Live Server extension
# Right-click index.html > Open with Live Server
```

---

## 📖 Usage Guide

### Step 1: Set Your Income
1. Enter your **Allowance** amount in the Income section
2. Enter any **Part-time Job** earnings
3. Enter any **Other Income** (e.g., freelance, family support)
4. Your **Total Income** updates automatically

### Step 2: Plan Your Expenses
1. In the Expenses section, check the categories you want to budget for
2. Enter the planned amount for each checked category
3. For the "Other" category, type a custom label (e.g., "Phone Credit")
4. Click **"Save Planned Expenses"** to store your budget
5. Your **Total Planned Expenses** and **Budget Surplus** update instantly

### Step 3: Record Your Spending
1. Fill in the Expenditure Recorder form:
   - **Date** – select the transaction date (defaults to today)
   - **Category** – choose from the dropdown or select "Other" and type a custom name
   - **Description** – brief note about the expense
   - **Amount** – the amount spent in Malawi Kwacha (MK)
2. Click **"➕ Add Entry"** to save the transaction
3. The transaction appears in the table below
4. All summary calculations update automatically

### Step 4: Monitor Your Progress
- **Summary Dashboard** – view your income, planned expenses, actual expenses, and savings
- **Progress Bar** – see what percentage of your budget you've spent
- **Spending Trend** – "On Track" means you're within budget; "Over Budget" means you've exceeded it
- **Budget Alert** – a warning banner appears if you overspend
- **Pie Chart** – visual breakdown of spending by category

### Step 5: Manage Your Data
- **Save Planned Expenses** – persists your budget to localStorage
- **Export JSON** – download a full backup of all your data
- **Export CSV** – download your transactions for spreadsheet analysis
- **Import JSON** – restore data from a backup file
- **Clear Month** – reset everything and start fresh (with confirmation)

---

## 🧰 Technologies Used

| Technology | Purpose |
|------------|---------|
| **HTML5** | Semantic structure and layout |
| **CSS3** | Responsive design, flexbox, grid, custom properties |
| **Vanilla JavaScript** | Core logic, DOM manipulation, event handling |
| **Canvas API** | Rendering the spending breakdown pie chart |
| **LocalStorage API** | Persistent data storage across sessions |

**No frameworks, no dependencies!** Everything is self-contained in a single HTML file.

---

## 📁 Project Structure

```
malawi-student-budget-planner/
│
├── index.html          # Complete application (HTML + CSS + JS)
├── README.md           # This documentation file
└── LICENSE             # MIT License
```

The entire application is contained in a single `index.html` file for simplicity and ease of deployment.

---

## ⚙️ How It Works

### Data Flow
1. **User Input** – User enters data via forms and checkboxes
2. **State Update** – Data is stored in the `state` JavaScript object
3. **Calculation** – `updateAll()` function recalculates all totals
4. **UI Update** – DOM elements are updated with new values
5. **Chart Refresh** – `drawPieChart()` redraws the spending breakdown
6. **Persistence** – `saveState()` writes to localStorage

### Core Functions

| Function | Description |
|----------|-------------|
| `updateAll()` | Central calculation engine – updates income, planned, actual, savings, progress bar, alerts, trend, and chart |
| `saveExpenses()` | Reads expense inputs, updates state, triggers `updateAll()` and `saveState()` |
| `addTransaction()` | Adds a new transaction, re-renders the table, updates calculations, saves state |
| `deleteTransaction()` | Removes a transaction by ID, updates calculations, saves state |
| `drawPieChart()` | Aggregates transactions by category and renders a canvas pie chart |
| `renderExpenseList()` | Dynamically builds the expense checklist from state |
| `renderTransactions()` | Renders the transaction table from state |
| `exportJSON()` / `exportCSV()` | Exports data in different formats |
| `importJSON()` | Imports data from a JSON file and restores state |
| `clearMonth()` | Resets all data to defaults, updates month to current |

### State Object Structure
```javascript
{
  month: "August 2026",
  income: {
    allowance: 0,
    partTime: 0,
    other: 0
  },
  expenses: {
    food: { amount: 0, checked: false, customLabel: '' },
    transport: { amount: 0, checked: false, customLabel: '' },
    // ... all 10 categories
  },
  transactions: [
    { id: "abc123", date: "2026-08-15", category: "Food", description: "Lunch", amount: 1500 }
  ]
}
```

---

## 📱 Responsive Design

The application is fully responsive and optimized for all screen sizes:

| Device | Layout |
|--------|--------|
| **Desktop** (1200px+) | Full layout with side-by-side panels (Income + Expenses grid) |
| **Tablet** (700–1200px) | Grid adjusts to single column, charts remain visible |
| **Mobile** (<700px) | Single-column layout, touch-friendly inputs, stacked elements |
| **Small Mobile** (<500px) | Optimized for very small screens with minimal padding |

The pie chart, summary cards, and expense checklist all adapt to the available space.

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help improve the Malawi Student Budget Planner:

### How to Contribute
1. **Fork the repository** on GitHub
2. **Create a feature branch**:
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**:
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**:
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request** with a clear description of your changes

### Areas for Improvement
- [ ] **Monthly Trends** – Add a line chart showing spending trends over time
- [ ] **Recurring Transactions** – Support for weekly/monthly recurring expenses
- [ ] **Multi-Month Support** – Switch between different months and view historical data
- [ ] **User Accounts** – Cloud sync across devices (Firebase/Supabase integration)
- [ ] **Dark Mode** – Add a dark theme toggle
- [ ] **PWA** – Convert to a Progressive Web App for offline installation
- [ ] **Budget Categories** – Allow users to add custom categories to the checklist
- [ ] **Notifications** – Push notifications for budget alerts
- [ ] **Currency Switcher** – Support multiple currencies

### Code Style
- Use meaningful variable and function names
- Add comments for complex logic
- Follow existing indentation (2 spaces)
- Test your changes thoroughly before submitting

---

## 🗺️ Roadmap

| Version | Features |
|---------|----------|
| **v1.0** | Core features: Income tracking, Expense planner, Transaction recorder, Summary dashboard |
| **v1.1** | Pie chart, CSV export, JSON import/export |
| **v1.2** | Budget alerts, Spending trend indicator |
| **v1.3** | (Planned) Multi-month support, Recurring transactions |
| **v2.0** | (Planned) PWA, Cloud sync, Dark mode |

---

## 📄 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

You are free to:
- **Use** – use the software for any purpose
- **Modify** – change the software to suit your needs
- **Distribute** – share the software with others
- **Sublicense** – include the software in your own projects

---

## 🙏 Acknowledgments

- Designed specifically for **students in Malawi** with Malawi Kwacha (MK) as the default currency
- Built with **offline-first** principles – no internet required after initial load
- Inspired by the need for **accessible financial planning tools** for university students
- Special thanks to all contributors and users who provide feedback and suggestions

---

## 📧 Contact & Support

- **Author**: Owen Ndeule
- **GitHub**: [@owenndeule](https://github.com/owenndeule)
- **Email**: [owenndeule2005@gmail.com](owenndeule2005@gmail.com)
- **Issues**: Please report bugs via [GitHub Issues](https://github.com/owenndeule/malawi-student-budget-planner/issues)

---

## ⭐ Show Your Support

If you find this tool useful, please:
- ⭐ **Star** the repository on GitHub
- 🐛 **Report** any issues you encounter
- 💡 **Suggest** new features via GitHub Issues
- 📣 **Share** it with fellow students who need budget management

---

### Made with ❤️ for students in Malawi

*“Plan your money, secure your future.”*
