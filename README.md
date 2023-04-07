# expence

A personal finance tool that lets you track expenses and allows to see trends and analytics.

## Core Functionality

1. Users create categories of spending and enter amounts and specify income to help pay for the expenses
2. Users should be able to view their spending trends in each category on weekly, monthly and yearly intervals.
3. Users should be able to create financial goals.
4. Users should be able to create budgets on their categories

## Expense creation

User can create multiple expenses in whatever currency they like. They can specify income amount so the total amount after all the expenses can be calculated and they can adjust the expense amounts based on that calculation.

```java
class User {
    MetaData metadata;
    Currency currency;
}

class Expense {
    int userId;
    String name;
    String type;
    double amount;
    Date dueDate;
    double limit;
}

class Expenditure {
    int userId;
    Date timePeriod;
    List<Expense> expenses;
    double totalExpenditure;
    double income;
}
```

## Analytics

Analytics page for users to see their expenditure in a specific time period.

```java
class Metrics {
    Date fromDate;
    Date toDate;
    int userId;
    
    List<Expenditure> getExpenditure(Date fromDate, Date toDate);
}
```

## Goals

Goals for users to specify their money saving goals.

```java
class Goal {
    String name;
    double amount;
    Date goalDate;
}
```

## Budgeting

Users can create caps / limits on individual expense categories to help them budget. Refer to expense class above.

## Tech Stack

1. MongoDB - DB for permanent storage of data
1. Express JS - middle layer
1. React JS - front end
1. Node JS - backend server
1. GraphQL - for querying data

## Budget Theory

Main categories of spending are as follows:

1. Money you can’t avoid to pay - rent, bills etc. - 20-40%
2. Money you need for future - savings - 20-30%
3. Money you get to spend - food, groceries, shopping etc.

