# Bank Management System

A console-based banking simulator written in Java. It covers the operations you'd expect from a small bank: opening accounts, moving money in and out, transferring between customers, and keeping a record of what happened.

The project started as a way to get hands-on practice with object-oriented programming and with managing data in memory using Java's collection classes.

## What It Does

Everything runs through a text menu. From there you can open accounts, check and move balances, look people up, and review past activity — all backed by plain Java, with nothing external to install.

## Capabilities

- Open new accounts, with account numbers assigned automatically
- Pick an account type — Savings or Current — at creation time
- Move money in (deposit) or out (withdrawal)
- Send funds from one account to another
- Look up a balance or pull full account details
- Find accounts by searching a customer's name
- Edit a customer's stored name or phone number
- Pull up the full history of transactions on an account
- List every account still open
- Shut down an account once it's been drawn down to zero
- Catch bad input and invalid operations before they cause problems

## Built With

| Piece | What's used |
|---|---|
| Language | Java |
| Storage in memory | ArrayList |
| Reading input | Scanner |
| Timestamps | LocalDateTime |
| Design style | Object-oriented |

Nothing beyond the standard Java library is needed — no database, no third-party packages.

## Concepts It Exercises

Working through this project touches classes and objects, constructors, encapsulation, method design, access modifiers, ArrayList usage, control flow (loops, if-else, switch expressions), exception handling, and date/time handling via LocalDateTime — the core toolkit for basic OOP design in Java.

## Layout

```text
BankManagementSystem/
│
└── src/
    ├── Account.java
    ├── Bank.java
    ├── Transaction.java
    └── BankManagementSystem.java
```

### What Each File Does

`Account.java` models one customer's account — number, name, phone, account type, current balance, and that account's own transaction log — and carries the logic for deposits, withdrawals, and printing account info.

`Bank.java` sits above all the individual accounts and coordinates them: registering new ones, looking them up, running deposits/withdrawals/transfers, handling searches, listing accounts, and closing them out.

`Transaction.java` is a small record type holding what kind of transaction occurred, how much money was involved, when it happened, and a short note describing it.

`BankManagementSystem.java` is the entry point — it holds `main()` and drives the menu loop the user interacts with.

## How a Session Runs

```text
Start
  |
  v
Display Main Menu
  |
  v
Select Operation
  |
  +---- Create Account
  |
  +---- Deposit Money
  |
  +---- Withdraw Money
  |
  +---- Transfer Money
  |
  +---- Check Balance
  |
  +---- View Account
  |
  +---- Search Account
  |
  +---- Update Account
  |
  +---- Transaction History
  |
  +---- Display All Accounts
  |
  +---- Close Account
  |
  v
Validate Input
  |
  v
Perform Operation
  |
  v
Display Result
  |
  v
Return to Main Menu
  |
  v
Exit
```

## The Menu Itself

```text
========================================
        BANK MANAGEMENT SYSTEM
========================================

1. Create Account
2. Deposit Money
3. Withdraw Money
4. Transfer Money
5. Check Balance
6. View Account Details
7. Search Account
8. Update Account
9. Transaction History
10. Display All Accounts
11. Close Account
12. Exit

Enter your choice:
```

## Sample Session

### Opening an account

```text
Enter Customer Name: Rahul
Enter Phone Number: 9876543210
Enter Account Type: Savings
Enter Initial Deposit: 5000

Account created successfully!

Account Number: 1001
Customer Name: Rahul
Account Type: Savings
Balance: ₹5000
```

### Putting money in

```text
Enter Account Number: 1001
Enter Amount: 2000

Deposit successful!
New Balance: ₹7000
```

### Taking money out

```text
Enter Account Number: 1001
Enter Amount: 1000

Withdrawal successful!
Remaining Balance: ₹6000
```

### Sending money between accounts

```text
Enter Sender Account: 1001
Enter Receiver Account: 1002
Enter Amount: 2000

Transfer successful!
```

## Getting It Running

### Before You Start

You'll need JDK 17 or newer on your machine. Confirm it's there:

```bash
java -version
javac -version
```

### 1. Grab the source

Open the project in whatever editor you use — VS Code, IntelliJ, Eclipse, plain terminal — and move into the source folder:

```bash
cd BankManagementSystem/src
```

### 2. Build it

```bash
javac *.java
```

### 3. Launch it

```bash
java BankManagementSystem
```

## What It Won't Do

This is a learning exercise, not something you'd deploy as an actual bank system:

- Nothing is saved to disk — close the program and the data is gone
- No visual interface, just the console
- No real login or identity verification
- It doesn't talk to any outside banking system

Everything lives in an in-memory `ArrayList` for the duration of the run.

## Where This Could Go Next

- Hook it up to MySQL so data survives a restart
- Add login with PIN verification
- Build a JavaFX front end
- Generate PDF statements
- Split users into admin vs. customer roles
- Calculate interest on balances
- Produce richer transaction reports

## Why This Project Exists

It's meant to show, concretely, how a familiar process like running a bank account translates into Java: a user's input becomes data held in objects, those objects are instances of classes, the classes encode the rules of the system, and running those rules against the data is what produces the transactions and output you see on screen.

## At a Glance

| Item | Details |
|---|---|
| Name | Bank Management System |
| Language | Java |
| Type | Console application |
| Level | College mini-project |
| Database | None |
| Third-party libraries | None |
| Interface | Command line |

## License

Built for learning and coursework use.
