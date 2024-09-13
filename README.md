## ℹ️ Introduction

This is a repository intended to serve as a starting point for the coding kata Movie Rental.
If you have found this repo through google, please note this is usually a refactoring kata, popularized by the incredible Martin Fowler. However, for this Kata we just have some simple boiler plate java, jest tests, and the prompt to build our very own movie store.

## 🏁 How To Start
If you don't have Java installed:
    1. Install Java: `brew install corretto` or download it [here](https://docs.aws.amazon.com/corretto/)
    2. Set it as your default JVM: `export JAVA_HOME=$(/usr/libexec/java_home -v 22)`
      1. Check it was set properly: `echo $JAVA_HOME` should output /Library/Java/JavaVirtualMachines/amazon-corretto-22.jdk/Contents/Home

Once you have Java installed:
1. Clone this repository: `git clone https://github.com/CodelyTV/java-basic-skeleton`.
2. Execute some [Gradle lifecycle tasks](https://docs.gradle.org/current/userguide/java_plugin.html#lifecycle_tasks) in order to check everything is OK:
    i. Create [the project JAR](https://docs.gradle.org/current/userguide/java_plugin.html#sec:jar): `make build`
    ii. Run the tests and plugins verification tasks: `make test`
3. Start developing based off the prompt below.

----------------------------------------------------------------------------------
# Movie Rental Store Kata (from Scratch)

You are tasked with building a simple movie rental application for a local video store. The system needs to manage customer accounts, track movie rentals, and generate detailed statements for customers. The goal is to create a basic, functioning system that can handle customer transactions and return accurate billing information.

## Requirements:

### Customers:
- Customers rent movies from the store.
- Each customer has a name and a rental history.

### Movies:
- Movies have a title and a category (either Regular, Children’s, or New Release).
- The rental cost varies based on the category:
  - **Regular**: Base price for 2 days. After 2 days, additional charges apply.
  - **Children’s**: Base price for 3 days. After 3 days, additional charges apply.
  - **New Release**: Charges are per day.

### Rentals:
- Customers can rent one or more movies at a time.
- A rental is associated with a movie and the number of days rented.

### Billing:
- The system must calculate the rental cost based on the movie’s category and the number of days rented.

#### Example Pricing:
- **Regular**: $2 for the first 2 days, then $1.50 for each additional day.
- **Children’s**: $1.50 for the first 3 days, then $1.50 for each additional day.
- **New Release**: $3 per day.
- The total cost for each rental is summed up and shown in a customer’s statement.

### Frequent Renter Points:
- The store offers a frequent renter points system to reward customer loyalty.
- Customers earn 1 frequent renter point for each movie rented.
- For **New Releases**, customers earn an additional bonus point if rented for more than 1 day.

### Statement Generation:
The system should be able to generate a statement for a customer, detailing:
- The customer’s name.
- The movies rented, how long they were rented for, and the cost.
- The total amount owed and the total frequent renter points earned.

## Example Scenario:
**Customer**: John Doe

**Movies Rented**:
- "The Lion King" (Children’s) for 5 days.
- "Inception" (New Release) for 3 days.
- "The Godfather" (Regular) for 1 day.

The generated statement should show the rental breakdown, total cost, and frequent renter points earned.
Rental Record for John Doe

Movies Rented:
1. "The Lion King" - 5 days: $4.50
2. "Inception" - 3 days: $9.00
3. "The Godfather" - 1 day: $2.00

Total amount owed: $15.50
Frequent renter points earned: 4
