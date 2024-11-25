![](https://wat-images.s3.ap-south-1.amazonaws.com/images/blogs/code-quality-wtf.jpeg)
## Features

ARTICLE: https://refactoring.guru/es/refactoring/what-is-refactoring
## Technical debt

DEFINITION: **Technical debt** refers to the **cost of additional work or rework** that arises when developers take shortcuts, either intentionally or unintentionally, to speed up development. This could mean writing code that is functional but lacks clean, maintainable, and well-documented structure, leading to long-term challenges in readability, maintainability, and scalability.

![[Clean Code.png]]
ARTICLE: https://refactoring.guru/es/refactoring/technical-debt

## When to refactor

![[When to refactor.png]]
ARTICLE: https://refactoring.guru/es/refactoring/when

## Checklist of refactoring done _right way_

![[Checklist of refactoring done right way.png]]
ARTICLE: https://refactoring.guru/es/refactoring/how-to

## Principles
### Be consistent

Being consistent refers to maintaining a consistent pattern. This can include using consistent naming conventions, data structures, and interfaces throughout the system, as well as adhering to established design principles and best practices. Consistency can help to make the system more maintainable, understandable, and extendable.

| **Aspect**                    | **Good Practice** Summary                                                                                            | **Why It Matters**                                                                                |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| **Naming Conventions**        | Use consistent naming styles like camelCase for variables, PascalCase for classes, and meaningful names for clarity. | Improves readability and makes the purpose of each variable, function, or class clear.            |
| **Indentation**               | Stick to a uniform number of spaces or tabs (e.g., 2 or 4 spaces).                                                   | Makes code visually structured and prevents syntax issues in languages like Python.               |
| **File and Folder Structure** | Maintain a logical structure for files and folders based on functionality or modules.                                | Simplifies navigation and scales well as the project grows.                                       |
| **Error Handling**            | Follow a consistent pattern, such as logging errors with a single library or method.                                 | Ensures robust debugging and avoids hidden runtime issues.                                        |
| **Code Style Tools**          | Use linters and formatters (e.g., Prettier or ESLint) for consistent formatting across all files.                    | Saves time, reduces formatting debates, and enforces best practices automatically.                |
| **Logic Patterns**            | Solve similar problems using similar approaches (e.g., choose between `for` loops or `.map()` consistently).         | Reduces mental load and ensures predictable behavior across the codebase.                         |
| **Testing Practices**         | Follow a single framework (e.g., Jest for JavaScript) and organize test files uniformly.                             | Simplifies debugging, avoids redundant dependencies, and keeps the testing structure predictable. |
### Meaningful Names over comments

One of the core principles of writing clean code is prioritizing **meaningful names** over excessive comments. The goal is to make your code self-explanatory so that comments become a complement, not a crutch. Clear and descriptive names reduce the need for additional explanations and help developers quickly understand the intent and functionality.

|**Rule**|**Good Example**|**Bad Example**|**Why It Matters**|
|---|---|---|---|
|**Be Descriptive**|`remainingAttempts`|`x`|Descriptive names make the purpose clear and reduce reliance on comments.|
|**Use Pronounceable Names**|`totalRevenue`|`ttlRvnu`|Improves verbal communication about the code during meetings or reviews.|
|**Avoid Ambiguity**|`isActiveUser`|`status`|Removes confusion about what the variable or function represents.|
|**Reflect Action in Functions**|`fetchUserDetails()`|`doWork()`|Descriptive function names indicate exactly what the function does, eliminating the need for comments.|
|**Avoid Magic Numbers**|`SECONDS_IN_A_MINUTE = 60`|`int seconds = 60`|Clear names make constants more meaningful and reduce the need for explanatory comments.|
|**Context Matters**|`user.firstName` (inside User class)|`userName.first`|Naming conventions should align with the context and entity (e.g., properties inside a `User` class should reflect that entity).|
### Indentation and Code Style

Indentation and code style ensure code is visually structured, readable, and professional. Following consistent conventions makes collaboration easier and helps prevent errors in languages where indentation affects execution (e.g., Python).

|**Aspect**|**Good Practice**|**Why It Matters**|
|---|---|---|
|**Indentation**|Use 2 or 4 spaces consistently throughout your project. Avoid mixing tabs and spaces.|Improves readability and prevents alignment issues in different editors.|
|**Bracket Placement**|Choose a consistent style (e.g., K&R, Allman). Example: `{` on the same line or next line.|Helps teams follow a single convention, avoiding debates or confusion.|
|**Line Length**|Keep lines short (e.g., 80–120 characters).|Prevents horizontal scrolling and ensures readability on all devices.|
|**Whitespace**|Use blank lines to separate blocks of code logically. Avoid excessive or trailing spaces.|Improves code clarity and reduces distractions from unintentional formatting errors.|
|**Naming Style**|Use meaningful and consistent naming conventions (e.g., camelCase, PascalCase, snake_case).|Ensures names reflect their purpose and follow project standards.|
|**Comments Placement**|Place comments above the code they describe, not beside it (except short inline comments).|Avoids clutter and keeps code clean while still explaining its purpose.|
|**Code Grouping**|Group related variables, functions, or imports together.|Makes code easier to navigate and reduces mental load when reading.|
|**Tooling**|Use linters (e.g., ESLint for JavaScript, Black for Python) and formatters (e.g., Prettier) to enforce rules.|Automates style checks, saving time and ensuring consistent application of rules across the codebase.|
### Keep it Small

The **"Keep It Small"** principle emphasizes breaking code into small, manageable, and modular pieces. Small functions, classes, and files are easier to understand, maintain, and test. This principle minimizes complexity, fosters readability, and encourages reusability.

| **Aspect**         | **Best Practices**                                                                                    | **Why It Matters**                                                       |
| ------------------ | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Functions**      | Write functions that do one thing well and are concise (5–15 lines).                                  | Easier to test, debug, and understand.                                   |
| **Classes**        | Limit the number of methods and responsibilities in a class.                                          | Fosters modular, reusable design.                                        |
| **Files/Modules**  | A file should ideally contain one component, class, or logical unit of functionality.                 | Simplifies navigation and reduces merge conflicts in collaborative work. |
| **Blocks of Code** | Keep loops, conditionals, and other blocks under 15 lines. Extract helper functions when logic grows. | Makes code cleaner and easier to comprehend.                             |
| **Testing**        | Write small, focused tests for individual functions, classes, or modules.                             | Ensures high test coverage and isolates potential issues faster.         |

### Pure Functions

A **pure function** is a fundamental concept in functional programming and clean code. It ensures that a function's behavior is predictable and isolated by avoiding side effects and always producing the same output for the same input.

---

**Why Use Pure Functions?**

1. **Predictability**: Pure functions are easy to understand, test, and debug.
2. **Reusability**: They are highly reusable because they don’t depend on or alter external state.
3. **Testability**: Their deterministic nature simplifies unit testing, as you don’t need to set up or clean external state.
4. **Concurrency**: Pure functions can safely run in parallel or concurrently, as they don’t share mutable state.

|**Aspect**|**Pure Functions**|**Impure Functions**|
|---|---|---|
|**Deterministic**|Returns the same output for the same input.|Output depends on external factors like state, time, or randomness.|
|**Side Effects**|No modification of global variables, files, or databases.|Modifies external state (e.g., updates a global variable or writes to a file).|
|**Immutability**|Creates and returns new data structures without altering inputs.|Mutates the original inputs or shared state.|
|**Dependencies**|Operates only on its inputs.|Relies on or alters external data, like reading from a database.|
### Minimize Cyclomatic Complexity

Cyclomatic complexity is a measure of the structural complexity of a program, which is determined by the number of linearly independent paths through a program’s control flow. High cyclomatic complexity can make a program difficult to understand, test, and maintain, so it’s often desirable to minimize it in system architecture.

| **Aspect**            | **Best Practices**                                                                                       | **Why It Matters**                                                               |
| --------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **Functions**         | Limit each function to 10 or fewer independent paths. Split large functions into smaller ones.           | Keeps functions manageable and reduces testing overhead.                         |
| **Conditionals**      | Avoid deeply nested conditionals. Use early returns, guard clauses, or polymorphism to simplify logic.   | Improves readability and reduces the likelihood of errors.                       |
| **Switch Statements** | Use only when there are clear, unrelated branches. Avoid using `switch` for highly interdependent logic. | Reduces cognitive load and keeps decision-making transparent.                    |
| **Loops**             | Keep loops simple. Avoid combining multiple conditions or actions within a single loop.                  | Simplifies flow control and makes code more predictable.                         |
| **Tools**             | Use tools like ESLint, SonarQube, or Radon to measure complexity and enforce limits.                     | Provides actionable insights and helps maintain manageable complexity over time. |


---
### **Cyclomatic Complexity Examples in Java (Java 21 LTS)**

### **Example 1: High Cyclomatic Complexity**

**Problematic Code:**

```java
public String getOrderStatus(Order order) {
    if (order == null) {
        return "Invalid Order";
    }
    if (order.isPaid()) {
        if (order.isShipped()) {
            if (order.isDelivered()) {
                return "Delivered";
            } else {
                return "In Transit";
            }
        } else {
            return "Awaiting Shipment";
        }
    } else {
        return "Pending Payment";
    }
}
```

**Cyclomatic Complexity Calculation:**

1. `if (order == null)` → 1 path
2. `if (order.isPaid())` → 1 path
3. `if (order.isShipped())` → 1 path
4. `if (order.isDelivered())` → 1 path

**Total Complexity**: **4**

---

**Refactored Using Guard Clauses:**

```java
public String getOrderStatus(Order order) {
    if (order == null) return "Invalid Order";
    if (!order.isPaid()) return "Pending Payment";
    if (!order.isShipped()) return "Awaiting Shipment";
    return order.isDelivered() ? "Delivered" : "In Transit";
}
```

**New Cyclomatic Complexity**: **1 (per branch)**  
**Why This is Better**: It’s shorter, easier to read, and eliminates nesting by handling each case early.

---

### **Example 2: Using `switch` with Pattern Matching**

Java 21 introduces enhanced `switch` with pattern matching, which can replace multiple `if-else` branches.

**Problematic Code:**

```java
public String getDiscountType(Object customer) {
    if (customer instanceof RegularCustomer) {
        return "Regular Discount";
    } else if (customer instanceof PremiumCustomer) {
        return "Premium Discount";
    } else if (customer instanceof GuestCustomer) {
        return "Guest Discount";
    } else {
        return "No Discount";
    }
}
```

**Cyclomatic Complexity Calculation**:

1. `if (customer instanceof RegularCustomer)` → 1 path
2. `else if (customer instanceof PremiumCustomer)` → 1 path
3. `else if (customer instanceof GuestCustomer)` → 1 path

**Total Complexity**: **3**

---

**Refactored Using Pattern Matching for `switch`:**

```java
public String getDiscountType(Object customer) {
    return switch (customer) {
        case RegularCustomer rc -> "Regular Discount";
        case PremiumCustomer pc -> "Premium Discount";
        case GuestCustomer gc -> "Guest Discount";
        default -> "No Discount";
    };
}
```

**New Cyclomatic Complexity**: **1**  
**Why This is Better**: Pattern matching for `switch` simplifies the branching and directly maps the object type to its corresponding output.

---

### **Example 3: Refactoring with Polymorphism**

When multiple conditional branches depend on the type or state of an object, polymorphism can help reduce complexity.

**Problematic Code:**

```java
public double calculateShippingCost(Order order) {
    if (order instanceof DomesticOrder) {
        return ((DomesticOrder) order).getShippingRate() * 5.0;
    } else if (order instanceof InternationalOrder) {
        return ((InternationalOrder) order).getShippingRate() * 10.0;
    } else {
        return 0.0;
    }
}
```

**Cyclomatic Complexity**: **3**

---

**Refactored Using Polymorphism:**

Define an interface for shipping cost:

```java
public sealed interface Order permits DomesticOrder, InternationalOrder {
    double calculateShippingCost();
}

public final class DomesticOrder implements Order {
    private double shippingRate;
    public DomesticOrder(double shippingRate) { this.shippingRate = shippingRate; }
    @Override
    public double calculateShippingCost() {
        return shippingRate * 5.0;
    }
}

public final class InternationalOrder implements Order {
    private double shippingRate;
    public InternationalOrder(double shippingRate) { this.shippingRate = shippingRate; }
    @Override
    public double calculateShippingCost() {
        return shippingRate * 10.0;
    }
}
```

Now use polymorphism in the main code:

```java
public double calculateShippingCost(Order order) {
    return order.calculateShippingCost();
}
```

**New Cyclomatic Complexity**: **1**  
**Why This is Better**: Logic is delegated to specialized classes, improving readability and maintainability.

---

### **Example 4: Refactoring Loops**

Complex loops with multiple conditions and operations can increase complexity.

**Problematic Code:**

```java
public int countValidOrders(List<Order> orders) {
    int count = 0;
    for (Order order : orders) {
        if (order != null && order.isPaid() && order.isShipped()) {
            count++;
        }
    }
    return count;
}
```

**Cyclomatic Complexity Calculation**:

1. `for` loop → 1 path
2. `if (order != null)` → 1 path
3. `if (order.isPaid())` → 1 path
4. `if (order.isShipped())` → 1 path

**Total Complexity**: **4**

---

**Refactored Using Streams:**

```java
public int countValidOrders(List<Order> orders) {
    return (int) orders.stream()
            .filter(order -> order != null)
            .filter(Order::isPaid)
            .filter(Order::isShipped)
            .count();
}
```

**New Cyclomatic Complexity**: **1 (per filter)**  
**Why This is Better**: Stream API pipelines break logic into modular, reusable filters while reducing boilerplate code.

---

### **Cyclomatic Complexity Thresholds**

|**Threshold**|**Implication**|
|---|---|
|**1–10**|Good. Easy to understand and maintain.|
|**11–20**|Moderate. Consider refactoring.|
|**21–50**|High. The code is difficult to test and maintain. Aggressive refactoring is recommended.|
|**>50**|Very High. The code is unmanageable and needs significant restructuring.|

---

### **Tools for Measuring Cyclomatic Complexity in Java**

|**Tool**|**Purpose**|
|---|---|
|**SonarQube**|Provides cyclomatic complexity analysis.|
|**Checkstyle**|Enforces coding standards and complexity limits.|
|**PMD**|Detects overly complex methods or classes.|
|**IntelliJ IDEA**|Built-in code complexity analyzer.|

---

### **Cheatsheet: Minimize Cyclomatic Complexity in Java**

|**Best Practice**|**Why It Helps**|
|---|---|
|**Break Down Methods**|Reduces independent paths and keeps each method focused on a single responsibility.|
|**Use Guard Clauses**|Simplifies conditional structures by returning early for special cases.|
|**Leverage `switch`**|Replaces deeply nested `if-else` chains with clean branching logic.|
|**Apply Polymorphism**|Offloads complex decision-making to specialized classes, reducing branching in the main code.|
|**Adopt Streams**|Handles filtering, mapping, and aggregating collections with concise and modular pipelines.|

### Avoid Passing Nulls Booleans

###### **Why Avoid Passing `null`**

1. **Unclear Intent**: It’s not obvious why `null` is being passed, leading to ambiguity.
2. **Prone to Errors**: Handling `null` requires additional checks, which increase complexity and the risk of `NullPointerException`.
3. **Breaks Immutability**: Passing `null` to modify a reference can lead to unexpected behavior.
4. **Encourages Poor Design**: Often indicates that a function is doing too much or lacks clear input requirements.

---

###### **Why Avoid Passing `boolean`**

1. **Misleading**: A `boolean` parameter doesn’t reveal what the function will do with it.
2. **Hard to Read**: Calls like `update(true, false)` don’t convey the intent of the parameters.
3. **Encourages Multi-Purpose Functions**: Using `boolean` often leads to functions that handle multiple, unrelated tasks.
4. **Difficult to Extend**: Adding more options requires refactoring the method signature and logic.

---

###### **Best Practices**

|**Practice**|**Description**|**Why It Helps**|
|---|---|---|
|**Use Optional Instead of Null**|Use `Optional` to represent the presence or absence of a value.|Avoids `NullPointerException` and explicitly communicates missing values.|
|**Overload Methods**|Provide multiple method signatures for different use cases instead of passing a `boolean` flag.|Improves clarity and ensures functions focus on a single responsibility.|
|**Encapsulate Boolean Logic**|Replace boolean parameters with enums or polymorphism.|Makes intent explicit and avoids confusion over parameter meanings.|
|**Default to Non-Null Parameters**|Make parameters non-null by default and validate inputs.|Reduces the need for redundant null checks.|
|**Throw Exceptions for Nulls**|Explicitly reject `null` inputs using preconditions or assertions.|Forces callers to provide valid inputs and prevents downstream issues.|

---

###### **Examples**

#### **1. Avoid Passing `null`**

**Problematic Code:**

```java
public void setConfig(Config config) {
    if (config == null) {
        this.config = new DefaultConfig();
    } else {
        this.config = config;
    }
}
```

**Better Code (Using `Optional`):**

```java
public void setConfig(Optional<Config> config) {
    this.config = config.orElseGet(DefaultConfig::new);
}
```

---

#### **2. Avoid Passing `boolean`**

**Problematic Code:**

```java
public void updateUser(boolean isAdmin) {
    if (isAdmin) {
        // Admin-specific logic
    } else {
        // Regular user logic
    }
}
```

**Better Code (Overloaded Methods):**

```java
public void updateUserAsAdmin() {
    // Admin-specific logic
}

public void updateUserAsRegular() {
    // Regular user logic
}
```

**Alternative (Using Enums):**

```java
public enum UserRole {
    ADMIN, REGULAR
}

public void updateUser(UserRole role) {
    switch (role) {
        case ADMIN -> updateUserAsAdmin();
        case REGULAR -> updateUserAsRegular();
    }
}
```

---

#### **3. Preventing `null` Inputs**

**Problematic Code:**

```java
public void processOrder(Order order) {
    if (order == null) {
        // Handle null
    } else {
        // Process order
    }
}
```

**Better Code (Using Preconditions):**

```java
public void processOrder(Order order) {
    Objects.requireNonNull(order, "Order must not be null");
    // Process order
}
```

---

#### **4. Eliminating Boolean Flags**

**Problematic Code:**

```java
public void setFeature(boolean enableFeature) {
    if (enableFeature) {
        // Enable the feature
    } else {
        // Disable the feature
    }
}
```

**Better Code (Separate Methods):**

```java
public void enableFeature() {
    // Enable the feature
}

public void disableFeature() {
    // Disable the feature
}
```

---

### **Refactoring Booleans with Polymorphism**

**Problematic Code:**

```java
public double calculatePrice(boolean isPremiumCustomer, double price) {
    if (isPremiumCustomer) {
        return price * 0.9; // 10% discount
    } else {
        return price;
    }
}
```

**Better Code (Using Polymorphism):**

```java
public interface Customer {
    double calculatePrice(double price);
}

public class PremiumCustomer implements Customer {
    @Override
    public double calculatePrice(double price) {
        return price * 0.9;
    }
}

public class RegularCustomer implements Customer {
    @Override
    public double calculatePrice(double price) {
        return price;
    }
}

// Usage
Customer customer = new PremiumCustomer();
double finalPrice = customer.calculatePrice(100.0);
```

---

### **Tools for Detecting Issues**

|**Tool**|**Purpose**|
|---|---|
|**SonarQube**|Detects use of `null` and overuse of boolean parameters.|
|**Checkstyle**|Ensures code follows best practices for parameter validation.|
|**FindBugs (SpotBugs)**|Flags potential null pointer exceptions in code.|

---

### **Cheatsheet: Avoid Passing Nulls and Booleans**

|**Aspect**|**Avoid**|**Use Instead**|
|---|---|---|
|**Nulls**|Passing `null` to represent missing values.|Use `Optional` or overload methods with defaults.|
|**Booleans**|Boolean flags for behavior.|Use enums, polymorphism, or separate methods to clarify intent.|
|**Validation**|Skipping null checks or assuming non-null inputs.|Use `Objects.requireNonNull()` to enforce non-null arguments at the start of a method.|
|**Readability**|`doSomething(true, false)` without context.|Replace with expressive APIs like `enableFeature()` or `setMode(Mode.ENABLED)`.|

---

### **Key Takeaways**

- **Avoid `null`**: Use `Optional` or require valid non-null inputs by default.
- **Avoid `boolean`**: Use clear, descriptive alternatives like enums or method overloading.
- **Write Explicit Code**: Aim for readability and clarity, reducing the mental load on the developer reading or maintaining the code.
- **Improve Safety**: Using these practices reduces runtime errors and unexpected behavior.

Let me know if you’d like specific examples tailored to your use case!
### Keep Framework Code Distant
### Use Correct Constructs

### Keep Tests Independent
### Use Meaningful Names
### Code by Actor
### Command Query Separation
### Avoid Hasty Abstractions