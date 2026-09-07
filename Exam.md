# DevOps Lab Internal–1 — Complete Exam Answers

Below are **exam/practical-ready answers** for all the topics shown in your syllabus. I’ve kept the code simple so you can **write and explain it in the lab/viva**.

---

# 1. User Registration Form using HTML, CSS and JavaScript

### Aim

To create a user registration form for an event using HTML, CSS and JavaScript with validation.

### `index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Event Registration Form</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

<div class="container">
    <h2>Event Registration Form</h2>

    <form id="registrationForm">

        <label>First Name:</label>
        <input type="text" id="fname" required>

        <label>Last Name:</label>
        <input type="text" id="lname" required>

        <label>Date of Birth:</label>
        <input type="date" id="dob" required>

        <label>Gender:</label>
        <input type="radio" name="gender" value="Male"> Male
        <input type="radio" name="gender" value="Female"> Female

        <label>Father's Name:</label>
        <input type="text" id="father" required>

        <label>Mother's Name:</label>
        <input type="text" id="mother" required>

        <label>Address:</label>
        <textarea id="address" required></textarea>

        <label>Phone Number:</label>
        <input type="tel" id="phone" required>

        <label>Email ID:</label>
        <input type="email" id="email" required>

        <h3>Education Details</h3>

        <table>
            <tr>
                <th>Qualification</th>
                <th>Institution</th>
                <th>Year</th>
                <th>Percentage</th>
            </tr>

            <tr>
                <td>10th</td>
                <td><input type="text"></td>
                <td><input type="number"></td>
                <td><input type="number"></td>
            </tr>

            <tr>
                <td>12th</td>
                <td><input type="text"></td>
                <td><input type="number"></td>
                <td><input type="number"></td>
            </tr>

            <tr>
                <td>Graduation</td>
                <td><input type="text"></td>
                <td><input type="number"></td>
                <td><input type="number"></td>
            </tr>
        </table>

        <label>Upload Photo:</label>
        <input type="file" id="photo" accept="image/*" required>

        <label>Upload Signature:</label>
        <input type="file" id="signature" accept="image/*" required>

        <button type="submit">Register</button>
        <button type="reset">Reset</button>

    </form>
</div>

<script src="script.js"></script>

</body>
</html>
```

### `style.css`

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
}

.container {
    width: 700px;
    margin: 30px auto;
    background: white;
    padding: 25px;
    border-radius: 10px;
}

h2 {
    text-align: center;
}

label {
    display: block;
    margin-top: 12px;
    font-weight: bold;
}

input, textarea {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    box-sizing: border-box;
}

input[type="radio"] {
    width: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 10px;
}

th, td {
    border: 1px solid black;
    padding: 8px;
}

button {
    padding: 10px 20px;
    margin: 15px 5px 0 0;
    cursor: pointer;
}
```

### `script.js`

```javascript
document.getElementById("registrationForm").addEventListener("submit", function(event) {

    event.preventDefault();

    let phone = document.getElementById("phone").value;
    let email = document.getElementById("email").value;

    let phonePattern = /^[0-9]{10}$/;
    let emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

    if (!phonePattern.test(phone)) {
        alert("Enter a valid 10-digit phone number");
        return;
    }

    if (!emailPattern.test(email)) {
        alert("Enter a valid email address");
        return;
    }

    alert("Registration Successful!");

});
```

### Important points for viva

* **HTML** → creates the structure.
* **CSS** → provides styling.
* **JavaScript** → performs validation and interaction.
* `required` → makes a field mandatory.
* `type="email"` → validates email format.
* `type="file"` → allows file upload.
* JavaScript regular expressions are used for phone and email validation.

---

# 2. Git and GitHub Commands

## What is Git?

**Git** is a distributed version-control system used to track changes in source code.

## What is GitHub?

**GitHub** is a cloud-based platform used to host Git repositories and collaborate with developers.

### Important Git Commands

| Command                                  | Description                         |
| ---------------------------------------- | ----------------------------------- |
| `git --version`                          | Displays installed Git version      |
| `git config --global user.name "Name"`   | Sets Git username                   |
| `git config --global user.email "email"` | Sets Git email                      |
| `git init`                               | Creates a new Git repository        |
| `git status`                             | Shows current repository status     |
| `git add file.java`                      | Adds a file to staging area         |
| `git add .`                              | Adds all files                      |
| `git commit -m "message"`                | Saves staged changes                |
| `git log`                                | Displays commit history             |
| `git branch`                             | Displays branches                   |
| `git branch feature`                     | Creates a new branch                |
| `git checkout feature`                   | Switches branch                     |
| `git switch feature`                     | Switches branch                     |
| `git merge feature`                      | Merges branch                       |
| `git remote -v`                          | Displays remote repository          |
| `git remote add origin URL`              | Adds GitHub repository              |
| `git push origin main`                   | Uploads code to GitHub              |
| `git pull origin main`                   | Downloads and merges latest changes |
| `git clone URL`                          | Copies GitHub repository            |
| `git diff`                               | Shows changes                       |
| `git restore file`                       | Restores a file                     |

---

## Practical: Two Programming Files

Suppose we have:

```text
DevOpsProject/
│
├── Calculator.java
└── ReverseString.java
```

### Calculator.java

```java
public class Calculator {
    public static void main(String[] args) {
        int a = 10;
        int b = 5;

        System.out.println("Addition = " + (a + b));
        System.out.println("Subtraction = " + (a - b));
        System.out.println("Multiplication = " + (a * b));
        System.out.println("Division = " + (a / b));
    }
}
```

### ReverseString.java

```java
public class ReverseString {
    public static void main(String[] args) {

        String str = "HELLO";
        String rev = "";

        for (int i = str.length() - 1; i >= 0; i--) {
            rev = rev + str.charAt(i);
        }

        System.out.println("Original = " + str);
        System.out.println("Reverse = " + rev);
    }
}
```

### Commands

```bash
mkdir DevOpsProject
cd DevOpsProject

git init

git add Calculator.java
git commit -m "Added calculator program"

git add ReverseString.java
git commit -m "Added reverse string program"

git branch -M main

git remote add origin https://github.com/username/DevOpsProject.git

git push -u origin main
```

---

# 3. Source Code Management on GitHub

### Aim

To create a feature branch, add three programming files, commit the changes and push the branch to GitHub.

### Three files

```text
Addition.java
Factorial.java
Prime.java
```

### Addition.java

```java
public class Addition {
    public static void main(String[] args) {
        int a = 10, b = 20;
        System.out.println("Sum = " + (a + b));
    }
}
```

### Factorial.java

```java
public class Factorial {
    public static void main(String[] args) {

        int n = 5;
        int fact = 1;

        for (int i = 1; i <= n; i++) {
            fact = fact * i;
        }

        System.out.println("Factorial = " + fact);
    }
}
```

### Prime.java

```java
public class Prime {
    public static void main(String[] args) {

        int n = 17;
        boolean prime = true;

        for (int i = 2; i <= n / 2; i++) {
            if (n % i == 0) {
                prime = false;
                break;
            }
        }

        if (prime)
            System.out.println("Prime Number");
        else
            System.out.println("Not Prime");
    }
}
```

### Git commands

```bash
git init

git add .
git commit -m "Added three Java programs"

git branch feature-programs
git switch feature-programs

git add .
git commit -m "Updated programs"

git push -u origin feature-programs
```

### Branch structure

```text
main
  |
  └── feature-programs
          |
          ├── Addition.java
          ├── Factorial.java
          └── Prime.java
```

### To merge feature branch

```bash
git switch main
git merge feature-programs
git push origin main
```

---

# 4. Jenkins Installation and Setup

## What is Jenkins?

**Jenkins** is an open-source automation server used mainly for **Continuous Integration (CI) and Continuous Delivery/Deployment (CD).**

---

# Hardware Requirements

Minimum practical requirements:

* Processor: Dual-core processor or better
* RAM: 2 GB minimum
* Disk space: At least 10 GB
* Network connection
* Keyboard and mouse
* Monitor

For practical development, **4 GB or more RAM** is preferable.

---

# Software Requirements

* Windows/Linux/macOS
* Java/JDK
* Jenkins
* Git
* Web browser
* Internet connection
* GitHub account
* Maven, if required by the project

---

# 21 Jenkins Installation and Setup Steps

These are good steps to write in your practical record.

### Step 1

Install **Java/JDK** on the system.

### Step 2

Open Command Prompt/Terminal.

### Step 3

Check Java installation:

```bash
java -version
```

### Step 4

Download Jenkins installer/package.

### Step 5

Start the Jenkins installation.

### Step 6

Accept the license agreement.

### Step 7

Select the installation location.

### Step 8

Install Jenkins as a service.

### Step 9

Select the Java installation/JDK used by Jenkins.

### Step 10

Select the Jenkins service port.

Example:

```text
8080
```

### Step 11

Complete the installation.

### Step 12

Start the Jenkins service.

### Step 13

Open a web browser.

### Step 14

Enter:

```text
http://localhost:8080
```

### Step 15

Find the initial administrator password from the Jenkins installation directory/log.

### Step 16

Enter the initial administrator password.

### Step 17

Select **Install suggested plugins**.

### Step 18

Create the first Jenkins administrator account.

### Step 19

Configure the Jenkins URL.

### Step 20

Open the Jenkins dashboard.

### Step 21

Verify the environment by creating a test job and running it.

### Jenkins workflow

```text
Install Java
     ↓
Install Jenkins
     ↓
Start Jenkins
     ↓
Open localhost:8080
     ↓
Enter Initial Password
     ↓
Install Plugins
     ↓
Create Admin User
     ↓
Jenkins Dashboard
     ↓
Create Job
     ↓
Build
```

---

# 5(a). Jenkins Freestyle Project with Git Integration

### Aim

To create a Jenkins Freestyle project and integrate it with the GitHub repository containing the **user registration form**.

---

## Procedure

### Step 1

Open Jenkins.

```text
http://localhost:8080
```

### Step 2

Click:

```text
New Item
```

### Step 3

Enter project name:

```text
UserRegistration
```

### Step 4

Select:

```text
Freestyle project
```

### Step 5

Click **OK**.

### Step 6

Under **Source Code Management**, select:

```text
Git
```

### Step 7

Enter the GitHub repository URL.

Example:

```text
https://github.com/username/UserRegistration.git
```

### Step 8

Configure Git credentials if the repository requires authentication.

### Step 9

Select the branch:

```text
*/main
```

### Step 10

Go to **Build Steps**.

For a simple HTML project, you can use a shell/batch step to verify the files.

Linux:

```bash
echo "User Registration Project"
ls
```

Windows:

```cmd
echo User Registration Project
dir
```

### Step 11

Click **Save**.

### Step 12

Click:

```text
Build Now
```

### Step 13

Jenkins clones the GitHub repository.

### Step 14

Jenkins executes the configured build step.

### Step 15

Check **Console Output**.

---

## Freestyle workflow

```text
GitHub Repository
       ↓
Jenkins
       ↓
Freestyle Project
       ↓
Git Checkout
       ↓
Build
       ↓
Test
       ↓
Success / Failure
```

---

# 5(b). Jenkins Pipeline Project with Git Integration

### Aim

To create a Jenkins Pipeline project integrated with GitHub for a **Product Catalogue, Description and Search Form**.

---

# Project Structure

```text
ProductCatalogue/
│
├── index.html
├── style.css
└── script.js
```

---

## `index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Product Catalogue</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

<h1>Product Catalogue</h1>

<input type="text" id="search" placeholder="Search Product"
       onkeyup="searchProduct()">

<div id="products">

    <div class="product">
        <h2>Laptop</h2>
        <p>High-performance laptop</p>
    </div>

    <div class="product">
        <h2>Mobile</h2>
        <p>Smartphone with advanced features</p>
    </div>

    <div class="product">
        <h2>Headphones</h2>
        <p>Wireless noise-cancelling headphones</p>
    </div>

</div>

<script src="script.js"></script>

</body>
</html>
```

### `style.css`

```css
body {
    font-family: Arial;
    text-align: center;
    background: #f2f2f2;
}

.product {
    background: white;
    margin: 15px auto;
    padding: 15px;
    width: 400px;
    border-radius: 8px;
}

#search {
    padding: 10px;
    width: 300px;
}
```

### `script.js`

```javascript
function searchProduct() {

    let input = document.getElementById("search")
                    .value.toLowerCase();

    let products = document.getElementsByClassName("product");

    for (let i = 0; i < products.length; i++) {

        let name = products[i].innerText.toLowerCase();

        if (name.includes(input))
            products[i].style.display = "block";
        else
            products[i].style.display = "none";
    }
}
```

---

# Jenkins Pipeline

Create a file named:

```text
Jenkinsfile
```

Put it in the GitHub repository.

```groovy
pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/username/ProductCatalogue.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Product Catalogue'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Product Catalogue'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Product Catalogue Deployment Completed'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully'
        }

        failure {
            echo 'Pipeline failed'
        }
    }
}
```

> Replace `username` and repository name with your actual GitHub repository.

---

# Pipeline Procedure

1. Open Jenkins.
2. Click **New Item**.
3. Enter:

```text
ProductCatalogue
```

4. Select **Pipeline**.
5. Click **OK**.
6. Go to **Pipeline** section.
7. Select **Pipeline script from SCM**.
8. Select **Git**.
9. Enter GitHub repository URL.
10. Select branch `main`.
11. Specify:

```text
Jenkinsfile
```

12. Click **Save**.
13. Click **Build Now**.
14. Jenkins checks out the Git repository.
15. Jenkins executes the Pipeline stages.
16. Check the console output.

---

# Jenkins Pipeline Flow

```text
Developer
    ↓
GitHub Repository
    ↓
Jenkins
    ↓
Checkout
    ↓
Build
    ↓
Test
    ↓
Deploy
    ↓
Success
```

---

# JAVA PROGRAMS TO LEARN

---

# 1. Java Program for Basic Calculator Operations

### Program

```java
import java.util.Scanner;

public class Calculator {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        double a = sc.nextDouble();

        System.out.print("Enter second number: ");
        double b = sc.nextDouble();

        System.out.println("Addition = " + (a + b));
        System.out.println("Subtraction = " + (a - b));
        System.out.println("Multiplication = " + (a * b));

        if (b != 0) {
            System.out.println("Division = " + (a / b));
            System.out.println("Modulus = " + (a % b));
        } else {
            System.out.println("Division by zero is not possible");
        }

        sc.close();
    }
}
```

### Sample Output

```text
Enter first number: 10
Enter second number: 5

Addition = 15.0
Subtraction = 5.0
Multiplication = 50.0
Division = 2.0
Modulus = 0.0
```

---

# 2. Java Program to Reverse Letters in a String

```java
import java.util.Scanner;

public class ReverseString {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        String reverse = "";

        for (int i = str.length() - 1; i >= 0; i--) {
            reverse = reverse + str.charAt(i);
        }

        System.out.println("Original String: " + str);
        System.out.println("Reversed String: " + reverse);

        sc.close();
    }
}
```

### Example

```text
Input:  HELLO
Output: OLLEH
```

---

# 3. Java Program for Permutations and Combinations

### Formula

Permutation:

$$
nP r = \frac{n!}{(n-r)!}
$$

Combination:

$$
nC r = \frac{n!}{r!(n-r)!}
$$

### Program

```java
import java.util.Scanner;

public class PermutationCombination {

    static long factorial(int n) {

        long fact = 1;

        for (int i = 1; i <= n; i++) {
            fact = fact * i;
        }

        return fact;
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter n: ");
        int n = sc.nextInt();

        System.out.print("Enter r: ");
        int r = sc.nextInt();

        if (r > n) {
            System.out.println("r cannot be greater than n");
        } else {

            long permutation =
                factorial(n) / factorial(n - r);

            long combination =
                factorial(n) /
                (factorial(r) * factorial(n - r));

            System.out.println("nPr = " + permutation);
            System.out.println("nCr = " + combination);
        }

        sc.close();
    }
}
```

### Example

For:

```text
n = 5
r = 2
```

Output:

```text
nPr = 20
nCr = 10
```

---

# 4. Java Program to Find Missing Number in an Array

### Logic

For numbers from `1` to `n`:

$$
Sum = \frac{n(n+1)}{2}
$$

Missing number:

$$
Missing = ExpectedSum - ArraySum
$$

### Program

```java
import java.util.Scanner;

public class MissingNumber {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter n: ");
        int n = sc.nextInt();

        int[] arr = new int[n - 1];

        System.out.println("Enter array elements:");

        int actualSum = 0;

        for (int i = 0; i < n - 1; i++) {
            arr[i] = sc.nextInt();
            actualSum += arr[i];
        }

        int expectedSum = n * (n + 1) / 2;

        int missing = expectedSum - actualSum;

        System.out.println("Missing Number = " + missing);

        sc.close();
    }
}
```

### Example

```text
n = 5

Array:
1 2 3 5

Missing Number = 4
```

---

# 5. Java Program to Find Maximum Subarray Sum

This uses **Kadane's Algorithm**.

### Program

```java
import java.util.Scanner;

public class MaximumSubarraySum {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter array size: ");
        int n = sc.nextInt();

        int[] arr = new int[n];

        System.out.println("Enter array elements:");

        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        int currentSum = arr[0];
        int maxSum = arr[0];

        for (int i = 1; i < n; i++) {

            currentSum = Math.max(arr[i],
                                  currentSum + arr[i]);

            maxSum = Math.max(maxSum, currentSum);
        }

        System.out.println("Maximum Subarray Sum = " + maxSum);

        sc.close();
    }
}
```

### Example

```text
Array:
-2 1 -3 4 -1 2 1 -5 4
```

Maximum subarray:

```text
4 -1 2 1
```

Therefore:

```text
Maximum Subarray Sum = 6
```

---

# ⭐ Most Important Things to Prepare for the Exam

### Theory/Viva

1. **What is Git?**
2. **What is GitHub?**
3. Difference between **Git and GitHub**
4. What is a repository?
5. What is staging?
6. What is a commit?
7. What is a branch?
8. What is merge?
9. What is Jenkins?
10. What is CI/CD?
11. What is a Jenkins Freestyle project?
12. What is a Jenkins Pipeline?
13. Difference between Freestyle and Pipeline.
14. What is a `Jenkinsfile`?
15. What is Git integration in Jenkins?
16. Why is source-code management important?
17. What are HTML, CSS and JavaScript?
18. Why is JavaScript validation used?

### ⭐ Commands to memorize

```bash
git init
git status
git add .
git commit -m "message"
git log
git branch
git switch
git merge
git clone
git remote -v
git remote add origin URL
git push origin main
git pull origin main
```

### ⭐ Jenkins flow to memorize

```text
GitHub
   ↓
Jenkins
   ↓
Checkout
   ↓
Build
   ↓
Test
   ↓
Deploy
```

**Best next step:** practice the **5 Java programs first**, then the **Git commands and Jenkins Freestyle/Pipeline procedure**—these are the easiest areas to reproduce quickly in a lab exam.
