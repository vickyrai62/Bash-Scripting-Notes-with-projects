# Comprehensive Bash Scripting Guide
## From Basic to Advanced for Cybersecurity Professionals

---

# 📋 MAIN INDEX (TABLE OF CONTENTS)

## 🚀 QUICK NAVIGATION
- [**BASIC LEVEL**](#basic-level) - Foundation concepts (11 topics)
- [**INTERMEDIATE LEVEL**](#intermediate-level) - Core programming (10 topics)  
- [**ADVANCED LEVEL**](#advanced-level) - Professional techniques (8 topics)
- [**CYBERSECURITY SECTION**](#cybersecurity-section) - Security applications (8 topics)
- [**EXTRA ADVANCED TOPICS**](extra-advanced-topics) - Expert-level features (7 topics)
- [**REFERENCE SECTION**](#-bash-scripting-reference---keywords--functions--variables) - Complete keywords & commands index
- [**CONCLUSION**](#conclusion) - Summary & next steps

---

# 📚 COMPREHENSIVE INDEXING

## 🔤 ALPHABETICAL INDEX (A-Z)
- **[A]** - [Arrays](#-array-operations), [Arithmetic Operators](#-arithmetic-operators), [alias](#-built-in-functions--commands), [awk](#-built-in-functions--commands)
- **[B]** - [break](#-essential-bash-keywords), [basename](#-built-in-functions--commands), [bg](#-built-in-functions--commands), [brace expansion](#-pattern-matching)
- **[C]** - [case](#-essential-bash-keywords), [continue](#-essential-bash-keywords), [cd](#-built-in-functions--commands), [chmod](#-built-in-functions--commands), [cp](#-built-in-functions--commands), [cut](#-built-in-functions--commands)
- **[D]** - [do](#-essential-bash-keywords), [done](#-essential-bash-keywords), [dirname](#-built-in-functions--commands), [date](#-built-in-functions--commands), [df](#-built-in-functions--commands), [du](#-built-in-functions--commands)
- **[E]** - [else](#-essential-bash-keywords), [elif](#-essential-bash-keywords), [esac](#-essential-bash-keywords), [exit](#-essential-bash-keywords), [exec](#-built-in-functions--commands), [export](#-built-in-functions--commands), [echo](#-built-in-functions--commands)
- **[F]** - [for](#-essential-bash-keywords), [fi](#-essential-bash-keywords), [find](#-built-in-functions--commands), [fg](#-built-in-functions--commands), [file functions](#-file-functions)
- **[G]** - [grep](#-built-in-functions--commands), [globbing](#-pattern-matching), [group operations](#-logical-operators)
- **[H]** - [here document](#-redirection-keywords), [here string](#-redirection-keywords), [head](#-built-in-functions--commands)
- **[I]** - [if](#-essential-bash-keywords), [in](#-essential-bash-keywords), [IFS](#-special-variables), [id](#-built-in-functions--commands)
- **[J]** - [jobs](#-built-in-functions--commands), [job control](#-job-control)
- **[K]** - [kill](#-built-in-functions--commands), [killall](#-built-in-functions--commands)
- **[L]** - [ls](#-built-in-functions--commands), [logical operators](#-logical-operators), [loop control](#-essential-bash-keywords)
- **[M]** - [mkdir](#-built-in-functions--commands), [mv](#-built-in-functions--commands), [man](#-built-in-functions--commands)
- **[N]** - [not](#-logical-operators), [nohup](#-job-control)
- **[O]** - [operators](#-arithmetic-operators), [options](#-shell-options)
- **[P]** - [pipe](#-redirection-keywords), [ps](#-built-in-functions--commands), [pwd](#-built-in-functions--commands), [printf](#-built-in-functions--commands), [pattern matching](#-pattern-matching)
- **[Q]** - [quotes](#-quote-types), [quiet mode](#-shell-options)
- **[R]** - [return](#-essential-bash-keywords), [read](#-built-in-functions--commands), [rm](#-built-in-functions--commands), [redirection](#-redirection-keywords)
- **[S]** - [signals](#-signals), [sort](#-built-in-functions--commands), [sed](#-built-in-functions--commands), [sleep](#-built-in-functions--commands), [source](#-built-in-functions--commands), [string operations](#-string-operations), [system functions](#-system-functions)
- **[T]** - [then](#-essential-bash-keywords), [test](#-test-operators), [touch](#-built-in-functions--commands), [tr](#-built-in-functions--commands), [type](#-built-in-functions--commands)
- **[U]** - [until](#-essential-bash-keywords), [unset](#-built-in-functions--commands), [user functions](#-built-in-functions--commands)
- **[V]** - [variables](#-special-variables), [validation](#-test-operators)
- **[W]** - [while](#-essential-bash-keywords), [wc](#-built-in-functions--commands), [which](#-built-in-functions--commands), [wildcards](#-pattern-matching)
- **[X]** - [exec](#-built-in-functions--commands), [export](#-built-in-functions--commands)
- **[Y]** - [yes](#-built-in-functions--commands)
- **[Z]** - [zenity](#-built-in-functions--commands), [zsh](#-shell-options)

## 📂 CATEGORY INDEX
- **[Control Flow]** - [if/else/fi](#-essential-bash-keywords), [case/esac](#-essential-bash-keywords), [for/do/done](#-essential-bash-keywords), [while/do/done](#-essential-bash-keywords), [until/do/done](#-essential-bash-keywords)
- **[Data Types]** - [Strings](#-string-operations), [Arrays](#-array-operations), [Numbers](#-arithmetic-operators), [Files](#-file-functions)
- **[File Operations]** - [File I/O](#-file-functions), [Redirection](#-redirection-keywords), [Permissions](#-built-in-functions--commands)
- **[Process Management]** - [Background Jobs](#-job-control), [Signals](#-signals), [Process Control](#-system-functions)
- **[Text Processing]** - [String Functions](#-string-functions), [Pattern Matching](#-pattern-matching), [Text Filters](#-built-in-functions--commands)
- **[System Administration]** - [User Management](#-system-functions), [System Info](#-system-functions), [Environment](#-special-variables)
- **[Security]** - [Permissions](#-built-in-functions--commands), [Validation](#-test-operators), [Secure Scripting](#-shell-options)

## 🎯 SKILL LEVEL INDEX
- **[Beginner]** - [Basic Keywords](#-essential-bash-keywords), [Simple Variables](#-special-variables), [Basic Commands](#-built-in-functions--commands)
- **[Intermediate]** - [Arrays](#-array-operations), [String Operations](#-string-operations), [Redirection](#-redirection-keywords)
- **[Advanced]** - [Process Control](#-job-control), [Signals](#-signals), [Pattern Matching](#-pattern-matching)
- **[Expert]** - [Shell Options](#-shell-options), [Advanced Operators](#-arithmetic-operators), [Complex Operations](#-string-operations)

## 🔍 SEARCH INDEX
- **[Conditional Logic]** - [if](#-essential-bash-keywords), [test](#-test-operators), [logical operators](#-logical-operators)
- **[Loops & Iteration]** - [for](#-essential-bash-keywords), [while](#-essential-bash-keywords), [until](#-essential-bash-keywords), [break](#-essential-bash-keywords), [continue](#-essential-bash-keywords)
- **[Data Manipulation]** - [strings](#-string-operations), [arrays](#-array-operations), [arithmetic](#-arithmetic-operators)
- **[File System]** - [file operations](#-file-functions), [directory operations](#-built-in-functions--commands), [permissions](#-built-in-functions--commands)
- **[Process & System]** - [process management](#-job-control), [system information](#-system-functions), [environment](#-special-variables)

---

# BASIC LEVEL

## 1. [What is Bash?](#what-is-bash)
- Definition and explanation
- Real-life and cybersecurity use cases
- Basic syntax and examples

## 2. [Shell vs Bash](#shell-vs-bash)
- Understanding shell types
- Available shells comparison
- Version checking methods

## 3. [Script Structure (Shebang, Comments)](#script-structure-shebang-comments)
- Shebang line importance
- Comment best practices
- Script documentation standards

## 4. [Running a Bash Script](#running-a-bash-script)
- Execution methods comparison
- Permission management
- Security implications

## 5. [Variables](#variables)
- Variable creation and usage
- Data types and scope
- Best practices

## 6. [User Input](#user-input)
- Reading user input
- Input validation
- Secure input handling

## 7. [Super / Special Variables](#super--special-variables)
- Predefined variables reference
- Script parameter handling
- Process information

## 8. [Quotes (Single, Double, Backticks)](#quotes-single-double-backticks)
- Quote types and behavior
- Variable expansion control
- Command substitution

## 9. [Arithmetic Operations](#arithmetic-operations)
- Integer arithmetic methods
- Floating-point calculations
- Mathematical expressions

## 10. [Conditional Statements (if, else, elif)](#conditional-statements-if-else-elif)
- Decision-making structures
- File and string comparisons
- Complex condition logic

## 11. [File and Directory Tests](#file-and-directory-tests)
- File existence checking
- Permission verification
- Directory operations

## 12. [Logical Operators (&&, ||, !)](#logical-operators--)
- Command chaining
- Conditional execution
- Error handling patterns

---

# INTERMEDIATE LEVEL

## 13. [Loops (for, while, until)](#loops-for-while-until)
- Loop types and syntax
- Array iteration
- Conditional looping

## 14. [Loop Control (break, continue)](#loop-control-break-continue)
- Loop interruption
- Iteration skipping
- Nested loop management

## 15. [Functions](#functions)
- Function creation and calling
- Parameter passing
- Return values

## 16. [Local vs Global Variables](#local-vs-global-variables)
- Variable scope management
- Best practices
- Memory considerations

## 17. [Case Statement](#case-statement)
- Multi-way conditionals
- Pattern matching
- Menu creation

## 18. [Arrays](#arrays)
- Array creation and manipulation
- Associative arrays
- Data structure operations

## 19. [String Operations](#string-operations)
- String manipulation techniques
- Pattern matching
- Text processing

## 20. [File Handling](#file-handling)
- File reading and writing
- Line-by-line processing
- File management

## 21. [Input/Output Redirection](#inputoutput-redirection)
- Stream redirection
- File descriptor management
- Advanced I/O techniques

## 22. [Pipes](#pipes)
- Command chaining
- Data processing pipelines
- Stream manipulation

## 23. [Exit Status and Error Handling](#exit-status-and-error-handling)
- Error detection and handling
- Exit code management
- Robust scripting

## 24. [Process Management](#process-management)
- Process control
- Background execution
- Resource monitoring

## 25. [Background & Foreground Jobs](#background--foreground-jobs)
- Job control techniques
- Process suspension
- Multi-tasking

---

# ADVANCED LEVEL

## 26. [Signals and Traps](#signals-and-traps)
- Signal handling
- Cleanup routines
- Graceful termination

## 27. [Debugging Bash Scripts](#debugging-bash-scripts)
- Debugging techniques
- Troubleshooting methods
- Performance analysis

## 28. [Bash Scripting Best Practices](#bash-scripting-best-practices)
- Code quality standards
- Security considerations
- Maintainability guidelines

## 29. [Automation with Cron Jobs](#automation-with-cron-jobs)
- Task scheduling
- Automated execution
- System maintenance

## 30. [Logging in Bash Scripts](#logging-in-bash-scripts)
- Log management
- Audit trails
- Monitoring implementation

## 31. [Secure Scripting Practices](#secure-scripting-practices)
- Security hardening
- Input validation
- Privilege management

## 32. [Performance Optimization](#performance-optimization)
- Efficiency techniques
- Resource optimization
- Speed improvements

## 33. [Bash Scripting for System Administration](#bash-scripting-for-system-administration)
- System automation
- Administrative tasks
- Server management

---

# CYBERSECURITY SECTION

## 34. [Bash Scripting for Cybersecurity Automation](#bash-scripting-for-cybersecurity-automation)
- Security automation basics
- Threat detection scripts
- Incident response automation

## 35. [Network Scanning Automation](#network-scanning-automation)
- Port scanning techniques
- Network discovery
- Vulnerability assessment

## 36. [Log Monitoring](#log-monitoring)
- Security log analysis
- Real-time monitoring
- Threat detection

## 37. [Incident Response](#incident-response)
- Automated response procedures
- Evidence preservation
- Threat containment

## 38. [SOC Operations](#soc-operations)
- Security operations center automation
- Alert triage
- Dashboard generation

## 39. [File Integrity Checking](#file-integrity-checking)
- Integrity monitoring
- Change detection
- Forensic analysis

## 40. [Malware Analysis Automation (Theoretical)](#malware-analysis-automation-theoretical)
- Static analysis techniques
- Behavioral monitoring
- Educational approaches

## 41. [Ethical Hacking Labs (TryHackMe / HTB – Legal Only)](#ethical-hacking-labs-tryhackme--htb--legal-only)
- Legal penetration testing
- Lab automation
- Security assessment

---

# EXTRA ADVANCED TOPICS

## 42. [Process Substitution](#process-substitution)
- Advanced I/O techniques
- Temporary file alternatives
- Data processing patterns

## 43. [Here Documents and Here Strings](#here-documents-and-here-strings)
- Multi-line input handling
- Configuration generation
- Script automation

## 44. [Coprocesses](#coprocesses)
- Bidirectional communication
- Interactive processes
- Advanced IPC

## 45. [Extended Globbing](#extended-globbing)
- Advanced pattern matching
- File selection techniques
- Complex filtering

## 46. [Brace Expansion](#brace-expansion)
- String generation
- Batch operations
- Command automation

## 47. [Named Pipes (FIFOs)](#named-pipes-fifos)
- Inter-process communication
- Data streaming
- Concurrent processing

## 48. [Mathematical Operations with bc](#mathematical-operations-with-bc)
- Advanced calculations
- Scientific computing
- Financial computations

---

# CONCLUSION

## 49. [Key Takeaways](#key-takeaways)
- Learning summary
- Best practices reminder
- Security considerations

## 50. [Next Steps](#next-steps)
- Continuous learning path
- Advanced topics exploration
- Professional development

---

**📊 GUIDE STATISTICS:**
- **Total Topics:** 50
- **Basic Level:** 12 topics
- **Intermediate Level:** 13 topics  
- **Advanced Level:** 8 topics
- **Cybersecurity:** 8 topics
- **Extra Advanced:** 7 topics
- **Examples per topic:** 1-3 complete scripts
- **Total Lines:** ~4,300+ lines

**🎯 LEARNING PATH:**
1. Start with **Basic Level** (topics 1-12)
2. Progress to **Intermediate Level** (topics 13-25)
3. Master **Advanced Level** (topics 26-33)
4. Specialize in **Cybersecurity** (topics 34-41)
5. Explore **Extra Advanced** (topics 42-48)
6. Review **Conclusion** (topics 49-50)

---

# BASIC LEVEL

## What is Bash?
**One-line Definition:** Bash is a command-line interpreter and scripting language for Unix/Linux systems.

**Short Explanation:** Bash (Bourne Again Shell) is the default shell on most Linux distributions. It allows users to execute commands, write scripts, and automate tasks through a powerful command-line interface.

**Syntax:**
```bash
#!/bin/bash
```

**Example:**
```bash
#!/bin/bash
echo "Hello, this is Bash!"
```

**Output:**
```
Hello, this is Bash!
```

**Real-life Use Case:** System administrators use Bash to manage servers, automate backups, and perform routine maintenance tasks.

**Cybersecurity Use Case:** Security analysts use Bash to automate log analysis, run security scans, and manage incident response procedures.

**Important Notes:** Bash is case-sensitive and follows specific command syntax rules. Always test scripts in a safe environment before production use.

---

## Shell vs Bash
**One-line Definition:** Shell is the general term for command-line interfaces, while Bash is a specific type of shell.

**Short Explanation:** Shell is any command-line interpreter (sh, zsh, csh, bash). Bash is an enhanced version of the original Bourne shell with additional features and improvements.

**Syntax:**
```bash
# Check current shell
echo $SHELL

# List available shells
cat /etc/shells
```

**Example:**
```bash
#!/bin/bash
echo "Current shell: $SHELL"
echo "Bash version: $BASH_VERSION"
```

**Output:**
```
Current shell: /bin/bash
Bash version: 5.1.16(1)-release
```

**Real-life Use Case:** Developers choose different shells based on features needed for their development environment.

**Cybersecurity Use Case:** Penetration testers may use different shells to avoid detection or utilize specific shell features for exploitation.

**Important Notes:** Bash scripts start with `#!/bin/bash` to specify the interpreter. Other shells have different shebang lines.

---

## Script Structure (Shebang, Comments)
**One-line Definition:** Bash scripts require a shebang line and can include comments for documentation.

**Short Explanation:** The shebang (`#!/bin/bash`) tells the system which interpreter to use. Comments start with `#` and are ignored by the interpreter but help humans understand the code.

**Syntax:**
```bash
#!/bin/bash
# This is a comment
# Author: Your Name
# Date: Current Date
# Description: Script purpose
```

**Example:**
```bash
#!/bin/bash
# System Information Script
# Author: Security Admin
# Date: 2025-01-28
# Description: Displays basic system information

echo "System Information"
echo "=================="
echo "Hostname: $(hostname)"
echo "Kernel: $(uname -r)"
```

**Output:**
```
System Information
==================
Hostname: ubuntu-server
Kernel: 5.15.0-91-generic
```

**Real-life Use Case:** Documentation helps team members understand script purpose and maintenance requirements.

**Cybersecurity Use Case:** Security scripts need clear documentation for audit trails and compliance requirements.

**Important Notes:** The shebang must be the first line of the script. Comments are crucial for code maintainability and team collaboration.

---

## Running a Bash Script
**One-line Definition:** Execute bash scripts using permission changes or direct interpreter calls.

**Short Explanation:** Scripts can be made executable and run directly, or called with the bash interpreter. Each method has different security implications and use cases.

**Syntax:**
```bash
# Method 1: Make executable and run
chmod +x script.sh
./script.sh

# Method 2: Run with bash interpreter
bash script.sh

# Method 3: Source the script
source script.sh
```

**Example:**
```bash
#!/bin/bash
# test_script.sh
echo "Script is running!"
echo "Current user: $(whoami)"
echo "Current directory: $(pwd)"
```

**Running the script:**
```bash
chmod +x test_script.sh
./test_script.sh
```

**Output:**
```
Script is running!
Current user: student
Current directory: /home/student
```

**Real-life Use Case:** System administrators schedule automated scripts to run at specific times using cron jobs.

**Cybersecurity Use Case:** Security teams deploy monitoring scripts across multiple servers for threat detection.

**Important Notes:** Always verify script permissions and source before execution. Use absolute paths in production scripts for reliability.

---

## Variables
**One-line Definition:** Variables store data values that can be referenced and manipulated in scripts.

**Short Explanation:** Variables in Bash hold text, numbers, or other data types. They are created without type declarations and accessed using the dollar sign prefix.

**Syntax:**
```bash
variable_name="value"
echo $variable_name
echo ${variable_name}
```

**Example:**
```bash
#!/bin/bash
# Variable examples
name="John Doe"
age=25
city="New York"
echo "Name: $name"
echo "Age: $age"
echo "City: $city"
echo "Full info: $name, $age years old, lives in $city"
```

**Output:**
```
Name: John Doe
Age: 25
City: New York
Full info: John Doe, 25 years old, lives in New York
```

**Real-life Use Case:** Store configuration settings, file paths, and user preferences in variables for easy maintenance.

**Cybersecurity Use Case:** Store security thresholds, alert email addresses, and log file locations in variables for security monitoring scripts.

**Important Notes:** Variable names are case-sensitive. No spaces around the equals sign. Use curly braces for clarity in complex expressions.

---

## User Input
**One-line Definition:** Read user input during script execution using the read command.

**Short Explanation:** The `read` command captures user input from the keyboard and stores it in variables for use within the script.

**Syntax:**
```bash
read variable_name
read -p "Prompt message" variable_name
read -s "Password prompt" variable_name
```

**Example:**
```bash
#!/bin/bash
# User input example
echo "User Registration Form"
echo "======================"
read -p "Enter your name: " name
read -p "Enter your email: " email
read -s -p "Enter your password: " password
echo
echo "Registration complete!"
echo "Name: $name"
echo "Email: $email"
echo "Password: [HIDDEN]"
```

**Output:**
```
User Registration Form
======================
Enter your name: Alice
Enter your email: alice@example.com
Enter your password: 
Registration complete!
Name: Alice
Email: alice@example.com
Password: [HIDDEN]
```

**Real-life Use Case:** Interactive installation scripts that collect user preferences and configuration details.

**Cybersecurity Use Case:** Security incident response scripts that collect investigation details from analysts.

**Important Notes:** Always validate user input for security. Use `-s` flag for sensitive data like passwords.

---

## Super / Special Variables
**One-line Definition:** Predefined variables that provide system and script information.

**Short Explanation:** Bash provides special variables that contain information about script parameters, process IDs, and execution status.

**Syntax:**
```bash
$0      # Script name
$1, $2  # Arguments
$#      # Number of arguments
$*      # All arguments
$@      # All arguments as separate words
$$      # Process ID
$?      # Exit status
$!      # Last background process ID
```

**Example:**
```bash
#!/bin/bash
echo "Script name: $0"
echo "Number of arguments: $#"
echo "All arguments: $*"
echo "Process ID: $$"
echo "Exit status: $?"

if [ $# -gt 0 ]; then
    echo "First argument: $1"
    echo "Second argument: $2"
fi
```

**Running with arguments:**
```bash
./special_vars.sh hello world 123
```

**Output:**
```
Script name: ./special_vars.sh
Number of arguments: 3
All arguments: hello world 123
Process ID: 12345
Exit status: 0
First argument: hello
Second argument: world
```

**Real-life Use Case:** Scripts that process command-line arguments for different operational modes.

**Cybersecurity Use Case:** Security tools that accept target IPs, ports, or scan types as command-line arguments.

**Important Notes:** Always check if required arguments are provided before using them. Use `$#` to validate argument count.

---

## Quotes (Single, Double, Backticks)
**One-line Definition:** Different quote types control how bash interprets text and variables.

**Short Explanation:** Single quotes preserve literal text, double quotes allow variable expansion, and backticks execute commands.

**Syntax:**
```bash
'Single quotes - literal text'
"Double quotes - variable expansion"
`Backticks - command execution`
$(...)    # Modern command substitution
```

**Example:**
```bash
#!/bin/bash
name="Alice"
echo 'Hello $name'           # Single quotes
echo "Hello $name"           # Double quotes
echo "Current date: `date`"  # Backticks
echo "Current user: $(whoami)" # Modern syntax
echo 'It\'s a test'         # Escaping in single quotes
echo "File: $HOME/file.txt"  # Variable expansion
```

**Output:**
```
Hello $name
Hello Alice
Current date: Tue Jan 28 10:30:00 EST 2025
Current user: alice
It's a test
File: /home/alice/file.txt
```

**Real-life Use Case:** Format strings for logging, file paths, and user messages with appropriate quoting.

**Cybersecurity Use Case:** Construct command strings for security scans while preventing injection attacks.

**Important Notes:** Use `$(...)` instead of backticks for better readability and nesting. Always quote variables to handle spaces.

---

## Arithmetic Operations
**One-line Definition:** Perform mathematical calculations using bash arithmetic expansion.

**Short Explanation:** Bash supports integer arithmetic using various syntaxes. Floating-point arithmetic requires external tools.

**Syntax:**
```bash
$((expression))
let expression
expr expression
bc for floating point
```

**Example:**
```bash
#!/bin/bash
# Arithmetic operations
a=10
b=5

echo "Addition: $((a + b))"
echo "Subtraction: $((a - b))"
echo "Multiplication: $((a * b))"
echo "Division: $((a / b))"
echo "Modulus: $((a % b))"

# Using let
let c=a+b
echo "Using let: $c"

# Increment/decrement
((a++))
echo "After increment: $a"

# Floating point with bc
echo "Floating point: $(echo "scale=2; 10/3" | bc)"
```

**Output:**
```
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2
Modulus: 0
Using let: 15
After increment: 11
Floating point: 3.33
```

**Real-life Use Case:** Calculate file sizes, time differences, and resource usage in system monitoring scripts.

**Cybersecurity Use Case:** Calculate risk scores, analyze time-based attack patterns, and process numerical security metrics.

**Important Notes:** Bash only supports integer arithmetic natively. Use `bc` for floating-point calculations.

---

## Conditional Statements (if, else, elif)
**One-line Definition:** Execute different code blocks based on condition evaluation.

**Short Explanation:** Conditional statements allow scripts to make decisions and execute different code paths based on boolean conditions.

**Syntax:**
```bash
if [ condition ]; then
    # code
elif [ condition ]; then
    # code
else
    # code
fi
```

**Example:**
```bash
#!/bin/bash
read -p "Enter your age: " age

if [ $age -lt 18 ]; then
    echo "Minor - Access denied"
elif [ $age -ge 18 ] && [ $age -lt 65 ]; then
    echo "Adult - Access granted"
else
    echo "Senior - Special access"
fi

# File existence check
if [ -f "/etc/passwd" ]; then
    echo "System file exists"
else
    echo "Critical file missing!"
fi
```

**Output:**
```
Enter your age: 25
Adult - Access granted
System file exists
```

**Real-life Use Case:** Check system requirements before software installation and provide appropriate feedback.

**Cybersecurity Use Case:** Validate user permissions, check security configurations, and implement access control logic.

**Important Notes:** Always quote variables in conditions to handle spaces and special characters. Use `[[ ]]` for advanced pattern matching.

---

## File and Directory Tests
**One-line Definition:** Check file properties and existence using test operators.

**Short Explanation:** Bash provides test operators to verify file existence, type, permissions, and other attributes before performing operations.

**Syntax:**
```bash
[ -f file ]     # Regular file exists
[ -d directory ] # Directory exists
[ -r file ]     # Readable
[ -w file ]     # Writable
[ -x file ]     # Executable
[ -s file ]     # Not empty
[ -e file ]     # Exists
```

**Example:**
```bash
#!/bin/bash
file="/var/log/syslog"
dir="/home/user"

echo "File and Directory Tests"
echo "========================"

if [ -f "$file" ]; then
    echo "✓ $file exists and is a regular file"
    if [ -r "$file" ]; then
        echo "✓ $file is readable"
    fi
    if [ -s "$file" ]; then
        echo "✓ $file is not empty"
    fi
else
    echo "✗ $file does not exist"
fi

if [ -d "$dir" ]; then
    echo "✓ $dir exists and is a directory"
else
    echo "✗ $dir does not exist"
fi
```

**Output:**
```
File and Directory Tests
========================
✓ /var/log/syslog exists and is a regular file
✓ /var/log/syslog is readable
✓ /var/log/syslog is not empty
✓ /home/user exists and is a directory
```

**Real-life Use Case:** Verify configuration files exist before starting services and check log file availability.

**Cybersecurity Use Case:** Validate security configuration files, check for suspicious files, and verify system integrity.

**Important Notes:** Always quote file paths to handle spaces. Use `-e` for general existence checks before specific tests.

---

## Logical Operators (&&, ||, !)
**One-line Definition:** Combine multiple conditions and control command execution flow.

**Short Explanation:** Logical operators allow combining conditions and creating conditional command chains based on success or failure.

**Syntax:**
```bash
&&    # AND - execute if previous succeeds
||    # OR - execute if previous fails
!     # NOT - invert condition
```

**Example:**
```bash
#!/bin/bash
echo "Logical Operators Demo"
echo "====================="

# AND operator
mkdir -p /tmp/test && echo "Directory created successfully"
cd /tmp/test && touch file.txt && echo "File created"

# OR operator
rm /tmp/test/file.txt || echo "File not found, but continuing"

# NOT operator
if [ ! -f "/nonexistent" ]; then
    echo "File does not exist (as expected)"
fi

# Combined logic
age=20
if [ $age -ge 18 ] && [ $age -lt 65 ]; then
    echo "Adult age range"
fi

# Command chaining
command -v git && echo "Git is installed" || echo "Git not found"
```

**Output:**
```
Logical Operators Demo
=====================
Directory created successfully
File created
File does not exist (as expected)
Adult age range
Git is installed
```

**Real-life Use Case:** Create directories only if parent creation succeeds, install dependencies only if missing.

**Cybersecurity Use Case:** Check multiple security conditions before allowing operations, implement fail-safe mechanisms.

**Important Notes:** `&&` and `||` are command operators, while `-a` and `-o` are test operators. Use appropriate operators for context.

---

# INTERMEDIATE LEVEL

## Loops (for, while, until)
**One-line Definition:** Repeat execution of code blocks multiple times based on conditions.

**Short Explanation:** Loops allow scripts to perform repetitive tasks efficiently by iterating through lists, counting, or checking conditions.

**Syntax:**
```bash
# For loop
for item in list; do
    # code
done

# While loop
while [ condition ]; do
    # code
done

# Until loop
until [ condition ]; do
    # code
done
```

**Example:**
```bash
#!/bin/bash
echo "Loop Examples"
echo "=============="

# For loop with array
fruits=("apple" "banana" "orange")
echo "Fruits:"
for fruit in "${fruits[@]}"; do
    echo "  - $fruit"
done

# For loop with range
echo "Numbers 1-5:"
for i in {1..5}; do
    echo "  Number: $i"
done

# While loop
counter=1
echo "While loop countdown:"
while [ $counter -le 3 ]; do
    echo "  Count: $counter"
    ((counter++))
done

# Until loop
echo "Until loop:"
until [ $counter -gt 6 ]; do
    echo "  Counter: $counter"
    ((counter++))
done
```

**Output:**
```
Loop Examples
==============
Fruits:
  - apple
  - banana
  - orange
Numbers 1-5:
  Number: 1
  Number: 2
  Number: 3
  Number: 4
  Number: 5
While loop countdown:
  Count: 1
  Count: 2
  Count: 3
Until loop:
  Counter: 4
  Counter: 5
  Counter: 6
  Counter: 7
```

**Real-life Use Case:** Process multiple files, generate reports for each user, or perform batch operations.

**Cybersecurity Use Case:** Scan multiple IP addresses, analyze log files in batches, or check security configurations across systems.

**Important Notes:** Always quote array expansions `"${array[@]}"`. Use `break` and `continue` for loop control.

---

## Loop Control (break, continue)
**One-line Definition:** Control loop execution flow with break and continue statements.

**Short Explanation:** `break` exits the loop entirely, while `continue` skips the current iteration and moves to the next one.

**Syntax:**
```bash
break [n]     # Exit n levels of loops
continue      # Skip current iteration
```

**Example:**
```bash
#!/bin/bash
echo "Loop Control Examples"
echo "===================="

# Break example
echo "Finding first multiple of 7:"
for i in {1..20}; do
    if [ $((i % 7)) -eq 0 ]; then
        echo "  Found: $i"
        break
    fi
done

# Continue example
echo "Even numbers 1-10:"
for i in {1..10}; do
    if [ $((i % 2)) -ne 0 ]; then
        continue
    fi
    echo "  $i"
done

# Nested loops with break
echo "Nested loop break:"
for i in {1..3}; do
    echo "Outer loop: $i"
    for j in {1..5}; do
        if [ $j -eq 3 ]; then
            break
        fi
        echo "  Inner loop: $j"
    done
done
```

**Output:**
```
Loop Control Examples
====================
Finding first multiple of 7:
  Found: 7
Even numbers 1-10:
  2
  4
  6
  8
  10
Nested loop break:
Outer loop: 1
  Inner loop: 1
  Inner loop: 2
Outer loop: 2
  Inner loop: 1
  Inner loop: 2
Outer loop: 3
  Inner loop: 1
  Inner loop: 2
```

**Real-life Use Case:** Skip invalid files during processing, stop searching when target is found.

**Cybersecurity Use Case:** Stop scanning when vulnerability is found, skip safe files during malware analysis.

**Important Notes:** `break` with a number exits multiple nested loop levels. Use descriptive comments for clarity.

---

## Functions
**One-line Definition:** Reusable code blocks that perform specific tasks.

**Short Explanation:** Functions organize code into logical units, promote reusability, and make scripts more maintainable and readable.

**Syntax:**
```bash
function_name() {
    # function body
    return value
}

# Alternative syntax
function function_name {
    # function body
}
```

**Example:**
```bash
#!/bin/bash
# Function definitions
greet_user() {
    local name=$1
    echo "Hello, $name!"
}

calculate_sum() {
    local num1=$1
    local num2=$2
    local sum=$((num1 + num2))
    echo $sum
}

check_file() {
    local file=$1
    if [ -f "$file" ]; then
        echo "File exists: $file"
        return 0
    else
        echo "File not found: $file"
        return 1
    fi
}

# Function calls
echo "Function Examples"
echo "================="
greet_user "Alice"

result=$(calculate_sum 10 20)
echo "Sum of 10 + 20 = $result"

check_file "/etc/passwd"
echo "Function exit status: $?"
```

**Output:**
```
Function Examples
=================
Hello, Alice!
Sum of 10 + 20 = 30
File exists: /etc/passwd
Function exit status: 0
```

**Real-life Use Case:** Create utility functions for common operations like logging, file validation, and user prompts.

**Cybersecurity Use Case:** Build security check functions, encryption/decryption routines, and vulnerability assessment tools.

**Important Notes:** Use `local` for function-specific variables. Functions can return values via `echo` or `return` for exit codes.

---

## Local vs Global Variables
**One-line Definition:** Control variable scope within functions using local and global declarations.

**Short Explanation:** Global variables are accessible throughout the script, while local variables are limited to function scope.

**Syntax:**
```bash
global_var="value"    # Global scope

function_name() {
    local local_var="value"  # Local scope
    global_var="new_value"   # Modifies global
}
```

**Example:**
```bash
#!/bin/bash
# Global variable
global_counter=0

increment_global() {
    global_counter=$((global_counter + 1))
    echo "Inside function - Global: $global_counter"
}

demonstrate_local() {
    local local_counter=10
    global_counter=$((global_counter + 5))
    echo "Inside function - Local: $local_counter"
    echo "Inside function - Global: $global_counter"
}

echo "Initial global counter: $global_counter"
increment_global
echo "After increment_global: $global_counter"
demonstrate_local
echo "After demonstrate_local: $global_counter"

# Try to access local variable (will be empty)
echo "Trying to access local_counter: $local_counter"
```

**Output:**
```
Initial global counter: 0
Inside function - Global: 1
After increment_global: 1
Inside function - Local: 10
Inside function - Global: 6
After demonstrate_local: 6
Trying to access local_counter: 
```

**Real-life Use Case:** Prevent variable name conflicts in large scripts, maintain clean separation between function data.

**Cybersecurity Use Case:** Isolate sensitive data within functions, prevent accidental exposure of security credentials.

**Important Notes:** Always declare variables as `local` in functions unless global access is specifically needed.

---

## Case Statement
**One-line Definition:** Multi-way conditional statement for pattern matching.

**Short Explanation:** Case statements provide cleaner syntax for comparing a variable against multiple patterns, replacing complex if-elif chains.

**Syntax:**
```bash
case $variable in
    pattern1)
        # code
        ;;
    pattern2)
        # code
        ;;
    *)
        # default case
        ;;
esac
```

**Example:**
```bash
#!/bin/bash
read -p "Enter a command (start/stop/restart/status): " command

case $command in
    "start")
        echo "Starting service..."
        echo "Service started successfully"
        ;;
    "stop")
        echo "Stopping service..."
        echo "Service stopped"
        ;;
    "restart"|"reload")
        echo "Restarting service..."
        echo "Service restarted"
        ;;
    "status")
        echo "Checking service status..."
        echo "Service is running"
        ;;
    *)
        echo "Unknown command: $command"
        echo "Available commands: start, stop, restart, status"
        ;;
esac

# Menu example
echo -e "\nMenu Selection:"
read -p "Choose option [1-4]: " choice

case $choice in
    1)
        echo "You selected: View files"
        ls -la
        ;;
    2)
        echo "You selected: System info"
        uname -a
        ;;
    3)
        echo "You selected: Disk usage"
        df -h
        ;;
    4)
        echo "You selected: Exit"
        exit 0
        ;;
    *)
        echo "Invalid option"
        ;;
esac
```

**Output:**
```
Enter a command (start/stop/restart/status): restart
Restarting service...
Service restarted

Menu Selection:
Choose option [1-4]: 2
You selected: System info
Linux ubuntu 5.15.0-91-generic #101-Ubuntu SMP Fri Nov 17 12:23:45 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
```

**Real-life Use Case:** Create interactive menus, process command-line arguments, handle user input validation.

**Cybersecurity Use Case:** Implement security level selection, process different attack types, handle incident response scenarios.

**Important Notes:** Use `|` for multiple patterns. `*` acts as wildcard for default case. Always end with `esac`.

---

## Arrays
**One-line Definition:** Data structures that store multiple values in a single variable.

**Short Explanation:** Arrays allow storing and manipulating collections of related data, supporting indexed access and iteration.

**Syntax:**
```bash
# Declaration
array_name=(value1 value2 value3)

# Access
${array_name[index]}
${array_name[@]}     # All elements
${#array_name[@]}    # Number of elements
```

**Example:**
```bash
#!/bin/bash
echo "Array Examples"
echo "=============="

# Array declaration
fruits=("apple" "banana" "orange" "grape")
numbers=(1 2 3 4 5)

# Access individual elements
echo "First fruit: ${fruits[0]}"
echo "Third number: ${numbers[2]}"

# All elements
echo "All fruits: ${fruits[@]}"
echo "All numbers: ${numbers[@]}"

# Array length
echo "Number of fruits: ${#fruits[@]}"
echo "Number of numbers: ${#numbers[@]}"

# Loop through array
echo "Iterating fruits:"
for fruit in "${fruits[@]}"; do
    echo "  - $fruit"
done

# Add elements
fruits+=("mango")
echo "After adding mango: ${fruits[@]}"

# Associative arrays (Bash 4+)
declare -A user_info
user_info["name"]="Alice"
user_info["age"]="25"
user_info["city"]="New York"

echo "User info:"
for key in "${!user_info[@]}"; do
    echo "  $key: ${user_info[$key]}"
done
```

**Output:**
```
Array Examples
==============
First fruit: apple
Third number: 3
All fruits: apple banana orange grape
All numbers: 1 2 3 4 5
Number of fruits: 4
Number of numbers: 5
Iterating fruits:
  - apple
  - banana
  - orange
  - grape
After adding mango: apple banana orange grape mango
User info:
  name: Alice
  age: 25
  city: New York
```

**Real-life Use Case:** Store configuration settings, process lists of files, manage user data collections.

**Cybersecurity Use Case:** Maintain lists of blocked IPs, store vulnerability data, process security event logs.

**Important Notes:** Use `"${array[@]}"` to preserve spaces in elements. Arrays are zero-indexed. Use `declare -A` for associative arrays.

---

## String Operations
**One-line Definition:** Manipulate and analyze text strings using built-in bash operations.

**Short Explanation:** Bash provides various string manipulation techniques for extracting, replacing, and analyzing text data.

**Syntax:**
```bash
${#string}           # Length
${string:position}   # Substring
${string:position:length}  # Substring with length
${string#pattern}    # Remove prefix
${string%pattern}    # Remove suffix
${string/pattern/replacement}  # Replace
```

**Example:**
```bash
#!/bin/bash
text="Hello World, Bash Programming"

echo "String Operations"
echo "================="
echo "Original string: $text"

# Length
echo "Length: ${#text}"

# Substring
echo "First 5 chars: ${text:0:5}"
echo "From position 6: ${text:6}"

# Find and replace
echo "Replace World with Universe: ${text/World/Universe}"

# Remove prefix/suffix
filename="document.txt"
echo "Remove extension: ${filename%.*}"
echo "Remove name: ${filename##*.}"

# Uppercase/lowercase
echo "Uppercase: ${text^^}"
echo "Lowercase: ${text,,}"

# Check if string contains another
if [[ $text == *"Bash"* ]]; then
    echo "String contains 'Bash'"
fi

# Split string (using IFS)
data="apple,banana,orange"
IFS=',' read -ra array <<< "$data"
echo "Split into array: ${array[@]}"
```

**Output:**
```
String Operations
=================
Original string: Hello World, Bash Programming
Length: 29
First 5 chars: Hello
From position 6: World, Bash Programming
Replace World with Universe: Hello Universe, Bash Programming
Remove extension: document
Remove name: txt
Uppercase: HELLO WORLD, BASH PROGRAMMING
Lowercase: hello world, bash programming
String contains 'Bash'
Split into array: apple banana orange
```

**Real-life Use Case:** Parse configuration files, process user input, format output strings.

**Cybersecurity Use Case:** Analyze log entries, extract IP addresses from logs, parse security alerts.

**Important Notes:** String operations are case-sensitive. Use `==` with `*` for substring matching. Use `IFS` for splitting strings.

---

## File Handling
**One-line Definition:** Read, write, and manipulate files using bash commands and redirection.

**Short Explanation:** File handling in bash includes reading file contents, writing data, appending to files, and managing file permissions.

**Syntax:**
```bash
# Reading files
cat file.txt
while read line; do
    echo "$line"
done < file.txt

# Writing files
echo "text" > file.txt     # Overwrite
echo "text" >> file.txt    # Append
```

**Example:**
```bash
#!/bin/bash
echo "File Handling Examples"
echo "===================="

# Create and write to file
echo "System Information Report" > report.txt
echo "Generated on: $(date)" >> report.txt
echo "Hostname: $(hostname)" >> report.txt
echo "Kernel: $(uname -r)" >> report.txt

# Read file line by line
echo -e "\nReading report.txt:"
while IFS= read -r line; do
    echo "Line: $line"
done < report.txt

# Check file properties
if [ -f "report.txt" ]; then
    echo -e "\nFile properties:"
    echo "Size: $(wc -c < report.txt) bytes"
    echo "Lines: $(wc -l < report.txt)"
    echo "Words: $(wc -w < report.txt)"
fi

# Copy and backup
cp report.txt report_backup.txt
echo "Backup created: report_backup.txt"

# Clean up
echo -e "\nCleaning up files..."
rm report.txt report_backup.txt
echo "Files removed"
```

**Output:**
```
File Handling Examples
====================

Reading report.txt:
Line: System Information Report
Line: Generated on: Tue Jan 28 10:30:00 EST 2025
Line: Hostname: ubuntu-server
Line: Kernel: 5.15.0-91-generic

File properties:
Size: 125 bytes
Lines: 4
Words: 16

Cleaning up files...
Files removed
```

**Real-life Use Case:** Create log files, generate reports, backup configuration files, process data files.

**Cybersecurity Use Case:** Analyze security logs, create incident reports, backup security configurations, process threat intelligence data.

**Important Notes:** Always check file existence before operations. Use `IFS=` to preserve leading/trailing spaces. Use quotes for filenames with spaces.

---

## Input/Output Redirection
**One-line Definition:** Control where commands get input from and where they send output.

**Short Explanation:** Redirection operators allow controlling the flow of data between commands, files, and devices.

**Syntax:**
```bash
> file      # Redirect stdout (overwrite)
>> file     # Redirect stdout (append)
< file      # Redirect stdin
2> file     # Redirect stderr
2>> file    # Redirect stderr (append)
&> file     # Redirect both stdout and stderr
```

**Example:**
```bash
#!/bin/bash
echo "I/O Redirection Examples"
echo "========================"

# Redirect stdout to file
echo "This goes to output.txt" > output.txt
echo "This is appended" >> output.txt

# Redirect stderr
ls /nonexistent 2> error.log
echo "Error captured in error.log"

# Redirect both stdout and stderr
{
    echo "Normal output"
    ls /nonexistent
} &> combined.log

# Here document
cat << EOF > config.txt
[Settings]
debug=true
timeout=30
logfile=/var/log/app.log
EOF

# Here string
grep "debug" <<< "debug=true timeout=30"

# Process substitution
diff <(echo "file1 content") <(echo "file2 content")

echo "Files created:"
ls -la *.txt *.log 2>/dev/null || echo "No files found"
```

**Output:**
```
I/O Redirection Examples
========================
Files created:
-rw-r--r-- 1 user user 45 Jan 28 10:30 config.txt
-rw-r--r-- 1 user user 25 Jan 28 10:30 error.log
-rw-r--r-- 1 user user 50 Jan 28 10:30 output.txt
-rw-r--r-- 1 user user 75 Jan 28 10:30 combined.log
```

**Real-life Use Case:** Save command output to files, capture errors for debugging, create configuration files.

**Cybersecurity Use Case:** Log security scan results, capture error messages from security tools, create incident reports.

**Important Notes:** Use `2>&1` to redirect stderr to stdout. Use `>/dev/null` to discard output. Here documents are useful for multi-line input.

---

## Pipes
**One-line Definition:** Connect command output to another command's input for data processing chains.

**Short Explanation:** Pipes allow creating powerful command chains where the output of one command becomes the input for the next command.

**Syntax:**
```bash
command1 | command2 | command3
```

**Example:**
```bash
#!/bin/bash
echo "Pipe Examples"
echo "============="

# Simple pipe
echo "hello world" | tr '[:lower:]' '[:upper:]'

# Multiple pipes
ps aux | grep bash | wc -l

# Complex processing chain
ls -la /var/log | grep "\.log$" | awk '{print $5, $9}' | sort -n

# Find and process
find /home -name "*.txt" 2>/dev/null | xargs wc -l | tail -1

# Network usage
netstat -tuln | grep LISTEN | awk '{print $4}' | cut -d':' -f2 | sort -n

# Log analysis
journalctl --since "1 hour ago" | grep -i error | wc -l

# System monitoring
top -b -n1 | head -5 | tail -1

echo "Pipe operations completed"
```

**Output:**
```
Pipe Examples
=============
HELLO WORLD
3
1254 /var/log/auth.log
8967 /var/log/syslog
2341 /var/log/kern.log
total 12567
Pipe operations completed
```

**Real-life Use Case:** Process log files, filter system information, analyze data streams, create monitoring dashboards.

**Cybersecurity Use Case:** Analyze security logs, filter network traffic, process intrusion detection data, monitor system activities.

**Important Notes:** Pipes create subprocesses. Use `xargs` for complex operations. Combine with `grep`, `awk`, `sed` for powerful text processing.

---

## Exit Status and Error Handling
**One-line Definition:** Check command success/failure using exit codes and handle errors appropriately.

**Short Explanation:** Every command returns an exit status (0 for success, non-zero for failure) that can be used for error handling and conditional logic.

**Syntax:**
```bash
command
echo $?        # Exit status of last command

if command; then
    echo "Success"
else
    echo "Failed"
fi
```

**Example:**
```bash
#!/bin/bash
echo "Exit Status and Error Handling"
echo "=============================="

# Successful command
ls /home > /dev/null
echo "ls /home exit status: $?"

# Failed command
ls /nonexistent > /dev/null 2>&1
echo "ls /nonexistent exit status: $?"

# Error handling in functions
check_service() {
    local service=$1
    if systemctl is-active --quiet "$service"; then
        echo "✓ $service is running"
        return 0
    else
        echo "✗ $service is not running"
        return 1
    fi
}

# Use error handling
echo "Checking services:"
for service in sshd udev networking; do
    check_service "$service"
    if [ $? -ne 0 ]; then
        echo "  Warning: $service needs attention"
    fi
done

# Set exit on error
set -e  # Exit immediately if a command exits with non-zero status
echo "Testing set -e:"
echo "This will run"
# echo "This would cause script to exit: false"
echo "This continues"

# Custom exit codes
validate_input() {
    if [ -z "$1" ]; then
        echo "Error: No input provided" >&2
        exit 1
    fi
    echo "Input is valid"
    exit 0
}

echo -e "\nTesting validation:"
validate_input "test input"
echo "Exit status: $?"
```

**Output:**
```
Exit Status and Error Handling
==============================
ls /home exit status: 0
ls /nonexistent exit status: 2
Checking services:
✓ sshd is running
✓ udev is running
✗ networking is not running
  Warning: networking needs attention
Testing set -e:
This will run
This continues

Testing validation:
Input is valid
Exit status: 0
```

**Real-life Use Case:** Validate file operations, check service status, handle network connectivity issues.

**Cybersecurity Use Case:** Validate security configurations, check authentication success, handle failed security scans.

**Important Notes:** Use `set -e` for strict error handling. Use `set -u` to treat unset variables as errors. Redirect errors to stderr (`>&2`).

---

## Process Management
**One-line Definition:** Control and monitor system processes using bash commands and signals.

**Short Explanation:** Process management involves starting, stopping, monitoring, and controlling system processes and their resource usage.

**Syntax:**
```bash
command &          # Run in background
jobs               # List background jobs
fg %n              # Bring job to foreground
bg %n              # Resume job in background
kill PID           # Terminate process
```

**Example:**
```bash
#!/bin/bash
echo "Process Management Examples"
echo "==========================="

# Start background process
sleep 10 &
bg_pid=$!
echo "Started background sleep process with PID: $bg_pid"

# List jobs
echo "Current jobs:"
jobs

# Check if process is running
if kill -0 $bg_pid 2>/dev/null; then
    echo "Process $bg_pid is still running"
else
    echo "Process $bg_pid has finished"
fi

# Process information
echo -e "\nProcess information:"
ps aux | head -5

# Find processes
echo -e "\nFinding bash processes:"
pgrep -l bash

# Kill background process
echo -e "\nKilling background process..."
kill $bg_pid
sleep 1

# Check again
if kill -0 $bg_pid 2>/dev/null; then
    echo "Process $bg_pid is still running"
else
    echo "Process $bg_pid has been terminated"
fi

# Resource monitoring
echo -e "\nSystem resource usage:"
echo "Memory usage:"
free -h
echo -e "\nDisk usage:"
df -h /
```

**Output:**
```
Process Management Examples
===========================
Started background sleep process with PID: 12345
Current jobs:
[1]+  Running                 sleep 10 &
Process 12345 is still running

Process information:
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.2  16856  1404 ?        Ss   10:00   0:01 /sbin/init
root           2  0.0  0.0      0     0 ?        S    10:00   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        I    10:00   0:00 [kworker/0:0]
root           4  0.0  0.0      0     0 ?        I    10:00   0:00 [kworker/0:0]

Finding bash processes:
12345 bash
12346 bash

Killing background process...
Process 12345 has been terminated

System resource usage:
Memory usage:
              total        used        free      shared  buff/cache   available
Mem:          3.8G        1.2G        2.1G         15M        512M        2.4G
Swap:         2.0G          0B        2.0G

Disk usage:
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        20G   8.5G   11G  45% /
```

**Real-life Use Case:** Monitor long-running processes, manage background tasks, optimize system resources.

**Cybersecurity Use Case:** Monitor suspicious processes, terminate malware, analyze process behavior, manage security tools.

**Important Notes:** Use `kill -9` as last resort. Always check if process exists before killing. Use `pgrep` and `pkill` for process management by name.

---

## Background & Foreground Jobs
**One-line Definition:** Control job execution in background and foreground for multitasking.

**Short Explanation:** Background jobs run without blocking the terminal, while foreground jobs require terminal access and can be suspended.

**Syntax:**
```bash
command &           # Start in background
Ctrl+Z              # Suspend foreground job
bg                  # Resume suspended job in background
fg                  # Bring background job to foreground
jobs                # List all jobs
kill %n             # Kill job by job number
```

**Example:**
```bash
#!/bin/bash
echo "Background and Foreground Job Management"
echo "========================================"

# Start multiple background jobs
echo "Starting background jobs..."
sleep 5 &   # Job 1
job1=$!
sleep 10 &  # Job 2
job2=$!
sleep 15 &  # Job 3
job3=$!

echo "Started 3 background jobs"
echo "Job list:"
jobs

# Check job status
echo -e "\nChecking job status:"
for job in $job1 $job2 $job3; do
    if kill -0 $job 2>/dev/null; then
        echo "Job $job is running"
    else
        echo "Job $job has finished"
    fi
done

# Wait for specific job
echo -e "\nWaiting for first job to finish..."
wait $job1
echo "First job (sleep 5) has finished"

# Bring remaining jobs to foreground one by one
echo -e "\nBringing next job to foreground..."
echo "Use 'fg' to bring job to foreground"
echo "Use 'Ctrl+Z' to suspend, then 'bg' to background"

# Clean up remaining jobs
echo -e "\nCleaning up remaining jobs..."
kill $job2 $job3 2>/dev/null
wait $job2 $job3 2>/dev/null
echo "All jobs completed"

# Demonstrate job control
echo -e "\nJob control demonstration:"
echo "Run: sleep 30 &"
echo "Then use: jobs, fg %1, bg %1, kill %1"
```

**Output:**
```
Background and Foreground Job Management
========================================
Starting background jobs...
Started 3 background jobs
Job list:
[1]   Running                 sleep 5 &
[2]-  Running                 sleep 10 &
[3]+  Running                 sleep 15 &

Checking job status:
Job 12347 is running
Job 12348 is running
Job 12349 is running

Waiting for first job to finish...
First job (sleep 5) has finished

Bringing next job to foreground...
Use 'fg' to bring job to foreground
Use 'Ctrl+Z' to suspend, then 'bg' to background

Cleaning up remaining jobs...
All jobs completed

Job control demonstration:
Run: sleep 30 &
Then use: jobs, fg %1, bg %1, kill %1
```

**Real-life Use Case:** Run multiple tasks simultaneously, manage long-running processes, optimize workflow efficiency.

**Cybersecurity Use Case:** Run multiple security scans concurrently, monitor various log sources simultaneously, manage parallel incident response tasks.

**Important Notes:** Use `%` prefix for job numbers, not PIDs. Use `wait` to synchronize job completion. Background jobs continue running after script ends.

---

# ADVANCED LEVEL

## Signals and Traps
**One-line Definition:** Handle system signals and create cleanup routines for graceful script termination.

**Short Explanation:** Signals are notifications sent to processes, while traps allow scripts to catch and handle these signals for cleanup and graceful shutdown.

**Syntax:**
```bash
trap 'command' SIGNAL    # Set trap
trap -l                  # List all signals
trap - SIGNAL            # Remove trap
```

**Example:**
```bash
#!/bin/bash
echo "Signal and Trap Examples"
echo "======================"

# Cleanup function
cleanup() {
    echo -e "\nCleaning up..."
    rm -f /tmp/tempfile.*
    echo "Cleanup completed"
    exit 0
}

# Set traps for different signals
trap cleanup EXIT          # Execute on script exit
trap cleanup SIGINT        # Ctrl+C
trap cleanup SIGTERM       # Termination signal

# Create temporary files
echo "Creating temporary files..."
touch /tmp/tempfile.1
touch /tmp/tempfile.2
touch /tmp/tempfile.3

echo "Temporary files created. Press Ctrl+C to test trap."

# Long-running process
for i in {1..10}; do
    echo "Working... $i/10"
    sleep 2
done

echo "Script completed normally"
```

**Output:**
```
Signal and Trap Examples
======================
Creating temporary files...
Temporary files created. Press Ctrl+C to test trap.
Working... 1/10
Working... 2/10
^C
Cleaning up...
Cleanup completed
```

**Real-life Use Case:** Ensure temporary files are cleaned up, close database connections, save work before termination.

**Cybersecurity Use Case:** Securely delete sensitive data on interruption, terminate security scans gracefully, log unexpected terminations.

**Important Notes:** Always use traps for cleanup operations. `EXIT` trap runs on normal completion. Use `SIGINT` for Ctrl+C handling.

---

## Debugging Bash Scripts
**One-line Definition:** Identify and fix script errors using debugging techniques and tools.

**Short Explanation:** Debugging involves tracing script execution, checking variable values, and identifying logic errors using built-in bash debugging features.

**Syntax:**
```bash
bash -x script.sh       # Execute with debugging
set -x                  # Enable debugging
set +x                  # Disable debugging
set -v                  # Verbose mode
```

**Example:**
```bash
#!/bin/bash
echo "Debugging Examples"
echo "=================="

# Enable debugging
set -x

# Function with potential error
divide_numbers() {
    local num1=$1
    local num2=$2
    
    echo "Dividing $num1 by $num2"
    if [ $num2 -eq 0 ]; then
        echo "Error: Division by zero" >&2
        return 1
    fi
    
    result=$((num1 / num2))
    echo "Result: $result"
}

# Test the function
divide_numbers 10 2
divide_numbers 10 0

# Disable debugging for cleaner output
set +x

echo -e "\nDebugging completed"
```

**Output with debugging:**
```
+ echo 'Debugging Examples'
+ echo '=================='
+ divide_numbers 10 2
+ local 'num1=10'
+ local 'num2=2'
+ echo 'Dividing 10 by 2'
Dividing 10 by 2
+ '[' 2 -eq 0 ']'
+ result=5
+ echo 'Result: 5'
Result: 5
+ divide_numbers 10 0
+ local 'num1=10'
+ local 'num2=0'
+ echo 'Dividing 10 by 0'
Dividing 10 by 0
+ '[' 0 -eq 0 ']'
+ echo 'Error: Division by zero'
Error: Division by zero
+ return 1
```

**Real-life Use Case:** Troubleshoot complex scripts, identify logic errors, optimize performance bottlenecks.

**Cybersecurity Use Case:** Debug security monitoring scripts, validate incident response procedures, analyze security tool behavior.

**Important Notes:** Use `set -e` to exit on errors. Use `set -u` to catch undefined variables. Use `set -o pipefail` for pipe error detection.

---

## Bash Scripting Best Practices
**One-line Definition:** Follow industry standards and conventions for writing maintainable bash scripts.

**Short Explanation:** Best practices ensure scripts are readable, maintainable, secure, and follow established coding standards.

**Syntax:**
```bash
#!/bin/bash
set -euo pipefail    # Strict error handling
IFS=$'\n\t'          # Safer IFS
```

**Example:**
```bash
#!/bin/bash
# Best Practices Example
# Author: Security Team
# Date: 2025-01-28
# Description: Secure file backup script

# Strict error handling
set -euo pipefail

# Safe IFS
IFS=$'\n\t'

# Constants
readonly SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
readonly LOG_FILE="/var/log/backup.log"
readonly BACKUP_DIR="/backup"

# Logging function
log() {
    local level=$1
    shift
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] [$level] $*" | tee -a "$LOG_FILE"
}

# Validation function
validate_backup_dir() {
    if [[ ! -d "$BACKUP_DIR" ]]; then
        log "ERROR" "Backup directory does not exist: $BACKUP_DIR"
        exit 1
    fi
}

# Main function
main() {
    log "INFO" "Starting backup process"
    
    validate_backup_dir
    
    # Backup files with error handling
    if cp -r /home/user/documents "$BACKUP_DIR/"; then
        log "INFO" "Backup completed successfully"
    else
        log "ERROR" "Backup failed"
        exit 1
    fi
}

# Execute main function
main "$@"
```

**Output:**
```
[2025-01-28 10:30:00] [INFO] Starting backup process
[2025-01-28 10:30:01] [INFO] Backup completed successfully
```

**Real-life Use Case:** Production scripts, team collaboration, code maintenance and reviews.

**Cybersecurity Use Case:** Security automation scripts, compliance reporting, incident response procedures.

**Important Notes:** Always use `set -euo pipefail`. Define constants with `readonly`. Use functions for modularity. Add comprehensive logging.

---

## Automation with Cron Jobs
**One-line Definition:** Schedule automatic script execution at specified times using cron.

**Short Explanation:** Cron is a time-based job scheduler that allows scripts to run automatically at predefined intervals or specific times.

**Syntax:**
```bash
crontab -e              # Edit cron jobs
crontab -l              # List cron jobs
* * * * * command       # Minute Hour Day Month Weekday
```

**Example:**
```bash
#!/bin/bash
# backup_script.sh - Automated backup script

LOG_FILE="/var/log/backup.log"
SOURCE_DIR="/home/user/documents"
BACKUP_DIR="/backup/$(date +%Y%m%d)"

# Create backup directory
mkdir -p "$BACKUP_DIR"

# Perform backup
if rsync -av "$SOURCE_DIR/" "$BACKUP_DIR/"; then
    echo "[$(date)] Backup successful: $BACKUP_DIR" >> "$LOG_FILE"
else
    echo "[$(date)] Backup failed" >> "$LOG_FILE"
    exit 1
fi

# Clean old backups (keep 7 days)
find /backup -type d -name "20*" -mtime +7 -exec rm -rf {} \; 2>/dev/null
```

**Cron configuration examples:**
```bash
# Edit crontab
crontab -e

# Add these lines:
0 2 * * * /home/user/scripts/backup_script.sh          # Daily at 2 AM
*/15 * * * * /home/user/scripts/monitor_script.sh      # Every 15 minutes
0 0 1 * * /home/user/scripts/monthly_report.sh         # Monthly on 1st
0 9 * * 1-5 /home/user/scripts/weekday_script.sh       # Weekdays at 9 AM
```

**Output in log file:**
```
[2025-01-28 02:00:00] Backup successful: /backup/20250128
[2025-01-29 02:00:00] Backup successful: /backup/20250129
```

**Real-life Use Case:** Automated backups, system maintenance, report generation, log rotation.

**Cybersecurity Use Case:** Security scans, log monitoring, vulnerability assessments, compliance checks.

**Important Notes:** Use absolute paths in cron jobs. Redirect output to log files. Test scripts manually before scheduling. Use proper permissions.

---

## Logging in Bash Scripts
**One-line Definition:** Record script activities and events for monitoring and debugging purposes.

**Short Explanation:** Logging provides a historical record of script execution, errors, and important events for troubleshooting and audit purposes.

**Syntax:**
```bash
echo "message" >> logfile
logger "message"    # System logger
```

**Example:**
```bash
#!/bin/bash
# Comprehensive logging example

# Configuration
readonly LOG_FILE="/var/log/security_monitor.log"
readonly LOG_LEVEL="${LOG_LEVEL:-INFO}"

# Log levels
declare -A LOG_LEVELS=([DEBUG]=0 [INFO]=1 [WARN]=2 [ERROR]=3)

# Logging function
log() {
    local level=$1
    shift
    local message="$*"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    
    # Check if we should log this level
    if [ ${LOG_LEVELS[$level]} -ge ${LOG_LEVELS[$LOG_LEVEL]} ]; then
        echo "[$timestamp] [$level] $message" | tee -a "$LOG_FILE"
        
        # Also send to system logger for errors
        if [ "$level" = "ERROR" ]; then
            logger -t security_monitor "ERROR: $message"
        fi
    fi
}

# Security monitoring functions
check_failed_logins() {
    local failed_count=$(grep "Failed password" /var/log/auth.log | grep "$(date '+%b %d')" | wc -l)
    
    if [ $failed_count -gt 10 ]; then
        log "ERROR" "High number of failed logins: $failed_count"
    elif [ $failed_count -gt 5 ]; then
        log "WARN" "Moderate failed logins: $failed_count"
    else
        log "DEBUG" "Failed logins within normal range: $failed_count"
    fi
}

check_disk_space() {
    local usage=$(df / | awk 'NR==2 {print $5}' | sed 's/%//')
    
    if [ $usage -gt 90 ]; then
        log "ERROR" "Critical disk usage: ${usage}%"
    elif [ $usage -gt 80 ]; then
        log "WARN" "High disk usage: ${usage}%"
    else
        log "INFO" "Disk usage normal: ${usage}%"
    fi
}

# Main execution
main() {
    log "INFO" "Starting security monitoring"
    
    check_failed_logins
    check_disk_space
    
    log "INFO" "Security monitoring completed"
}

main "$@"
```

**Output in log file:**
```
[2025-01-28 10:30:00] [INFO] Starting security monitoring
[2025-01-28 10:30:00] [WARN] Moderate failed logins: 7
[2025-01-28 10:30:00] [INFO] Disk usage normal: 65%
[2025-01-28 10:30:00] [INFO] Security monitoring completed
```

**Real-life Use Case:** Application logging, system monitoring, audit trails, performance tracking.

**Cybersecurity Use Case:** Security event logging, incident tracking, compliance auditing, intrusion detection.

**Important Notes:** Use structured logging formats. Include timestamps and log levels. Rotate log files to prevent disk overflow. Use appropriate permissions for log files.

---

## Secure Scripting Practices
**One-line Definition:** Write scripts that protect against security vulnerabilities and attacks.

**Short Explanation:** Secure scripting involves implementing safeguards against common security threats like injection attacks, privilege escalation, and data exposure.

**Syntax:**
```bash
# Input validation
[[ $input =~ ^[a-zA-Z0-9]+$ ]]
```

**Example:**
```bash
#!/bin/bash
# Secure scripting practices

# Security settings
set -euo pipefail
IFS=$'\n\t'

# Secure input validation
validate_input() {
    local input=$1
    local pattern=$2
    
    if [[ ! $input =~ $pattern ]]; then
        echo "Invalid input: $input" >&2
        exit 1
    fi
}

# Secure file operations
secure_file_write() {
    local file=$1
    local content=$2
    
    # Create directory if it doesn't exist
    mkdir -p "$(dirname "$file")"
    
    # Write with restricted permissions
    echo "$content" > "$file"
    chmod 600 "$file"
}

# Safe command execution
safe_execute() {
    local cmd=$1
    shift
    
    # Validate command
    case $cmd in
        ls|cat|grep|awk|sed)
            "$cmd" "$@"
            ;;
        *)
            echo "Command not allowed: $cmd" >&2
            exit 1
            ;;
    esac
}

# Example usage with security
main() {
    echo "Secure Script Demo"
    echo "=================="
    
    # Validate user input
    read -p "Enter filename (alphanumeric only): " filename
    validate_input "$filename" "^[a-zA-Z0-9._-]+$"
    
    # Secure file operation
    secure_file_write "/tmp/secure/$filename.txt" "Sensitive data"
    echo "File created securely"
    
    # Safe command execution
    read -p "Enter command to execute (ls/cat/grep): " cmd
    read -p "Enter argument: " arg
    validate_input "$arg" "^[a-zA-Z0-9._/-]+$"
    
    safe_execute "$cmd" "$arg"
}

# Run with reduced privileges if possible
if [ "$(id -u)" -eq 0 ]; then
    echo "Warning: Running as root is not recommended" >&2
fi

main "$@"
```

**Output:**
```
Secure Script Demo
==================
Enter filename (alphanumeric only): test_file
File created securely
Enter command to execute (ls/cat/grep): ls
Enter argument: /tmp/secure
test_file.txt
```

**Real-life Use Case:** Production scripts, user input processing, file management utilities.

**Cybersecurity Use Case:** Security tools, authentication scripts, data processing utilities.

**Important Notes:** Always validate user input. Use principle of least privilege. Avoid eval with user input. Use absolute paths. Set proper file permissions.

---

## Performance Optimization
**One-line Definition:** Improve script execution speed and resource efficiency through optimization techniques.

**Short Explanation:** Performance optimization involves reducing execution time, memory usage, and CPU consumption through efficient coding practices.

**Syntax:**
```bash
# Use built-in operations instead of external commands
${#variable}    # Instead of echo $variable | wc -c
```

**Example:**
```bash
#!/bin/bash
echo "Performance Optimization Examples"
echo "================================="

# Inefficient vs Efficient operations

# Inefficient: Using external commands
inefficient_count() {
    local file=$1
    echo $(cat "$file" | wc -l)    # Spawns cat and wc
}

# Efficient: Using built-in operations
efficient_count() {
    local file=$1
    local count=0
    while IFS= read -r line; do
        ((count++))
    done < "$file"
    echo $count
}

# Inefficient: Multiple external calls
inefficient_string() {
    local text=$1
    echo "$text" | wc -c           # External wc
}

# Efficient: Built-in parameter expansion
efficient_string() {
    local text=$1
    echo ${#text}                  # Built-in operation
}

# Performance comparison
echo "Testing string length calculation:"
text="This is a test string for performance comparison"

echo "Inefficient method:"
time for i in {1..1000}; do
    inefficient_string "$text" > /dev/null
done

echo "Efficient method:"
time for i in {1..1000}; do
    efficient_string "$text" > /dev/null
done

# Array operations optimization
echo -e "\nArray operations:"

# Create large array
large_array=()
for i in {1..10000}; do
    large_array+=("item_$i")
done

# Efficient array iteration
echo "Efficient array iteration:"
time for item in "${large_array[@]}"; do
    :  # No operation
done

# Use built-in string operations
echo -e "\nString operations:"
filename="document.backup.old.tar.gz"

# Efficient: Parameter expansion
echo "Extension: ${filename##*.}"
echo "Basename: ${filename%.*}"
echo "Directory: ${filename%/*}"

# Avoid subshells when possible
echo -e "\nAvoiding subshells:"
current_dir=$(pwd)  # Subshell
echo "Current dir: $current_dir"

current_dir=$PWD   # No subshell
echo "Current dir: $current_dir"
```

**Output:**
```
Performance Optimization Examples
=================================
Testing string length calculation:
Inefficient method:
real    0m3.456s
user    0m1.234s
sys     0m2.345s

Efficient method:
real    0m0.123s
user    0m0.045s
sys     0m0.078s

Array operations:
Efficient array iteration:
real    0m0.234s
user    0m0.156s
sys     0m0.078s

String operations:
Extension: gz
Basename: document.backup.old.tar
Directory: 

Avoiding subshells:
Current dir: /home/user
Current dir: /home/user
```

**Real-life Use Case:** Large data processing, batch operations, performance-critical scripts.

**Cybersecurity Use Case:** Log analysis, security scanning, network monitoring with large datasets.

**Important Notes:** Use built-in operations over external commands. Avoid unnecessary subshells. Minimize file I/O operations. Use appropriate data structures.

---

## Bash Scripting for System Administration
**One-line Definition:** Automate system management tasks using bash scripts for efficient administration.

**Short Explanation:** System administration scripts automate routine tasks like user management, service monitoring, and system maintenance.

**Syntax:**
```bash
# System commands
systemctl start service
useradd username
```

**Example:**
```bash
#!/bin/bash
# System Administration Script

# Configuration
readonly ADMIN_EMAIL="admin@company.com"
readonly LOG_FILE="/var/log/sysadmin.log"
readonly BACKUP_DIR="/backup"

# Logging function
log() {
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] $*" | tee -a "$LOG_FILE"
}

# System health check
check_system_health() {
    log "Starting system health check"
    
    # Check disk space
    local disk_usage=$(df / | awk 'NR==2 {print $5}' | sed 's/%//')
    if [ $disk_usage -gt 80 ]; then
        log "WARNING: High disk usage: ${disk_usage}%"
    fi
    
    # Check memory usage
    local mem_usage=$(free | awk 'NR==2{printf "%.0f", $3*100/$2}')
    if [ $mem_usage -gt 90 ]; then
        log "WARNING: High memory usage: ${mem_usage}%"
    fi
    
    # Check load average
    local load_avg=$(uptime | awk -F'load average:' '{print $2}' | awk '{print $1}' | sed 's/,//')
    if (( $(echo "$load_avg > 2.0" | bc -l) )); then
        log "WARNING: High load average: $load_avg"
    fi
}

# User management
create_user() {
    local username=$1
    local full_name=$2
    
    if id "$username" &>/dev/null; then
        log "ERROR: User $username already exists"
        return 1
    fi
    
    useradd -m -c "$full_name" "$username"
    echo "$username:$(openssl rand -base64 12)" | chpasswd
    passwd -e "$username"
    
    log "Created user: $username ($full_name)"
}

# Service management
manage_service() {
    local service=$1
    local action=$2
    
    case $action in
        start|stop|restart|status)
            systemctl "$action" "$service"
            log "Service $action: $service"
            ;;
        *)
            log "ERROR: Invalid service action: $action"
            return 1
            ;;
    esac
}

# Backup configuration
backup_configs() {
    local backup_date=$(date +%Y%m%d_%H%M%S)
    local backup_path="$BACKUP_DIR/configs_$backup_date"
    
    mkdir -p "$backup_path"
    
    # Backup important configuration files
    cp /etc/passwd "$backup_path/"
    cp /etc/group "$backup_path/"
    cp /etc/shadow "$backup_path/"
    tar -czf "$backup_path/etc_config.tar.gz" /etc/ 2>/dev/null
    
    log "Configuration backup completed: $backup_path"
}

# Main menu
main_menu() {
    PS3="Select an option: "
    options=("System Health Check" "Create User" "Manage Service" "Backup Configs" "Exit")
    
    select opt in "${options[@]}"; do
        case $opt in
            "System Health Check")
                check_system_health
                ;;
            "Create User")
                read -p "Username: " username
                read -p "Full Name: " full_name
                create_user "$username" "$full_name"
                ;;
            "Manage Service")
                read -p "Service name: " service
                read -p "Action (start/stop/restart/status): " action
                manage_service "$service" "$action"
                ;;
            "Backup Configs")
                backup_configs
                ;;
            "Exit")
                log "System administration tool exited"
                break
                ;;
            *)
                echo "Invalid option"
                ;;
        esac
    done
}

# Check if running as root
if [ "$(id -u)" -ne 0 ]; then
    echo "This script must be run as root" >&2
    exit 1
fi

main_menu "$@"
```

**Output:**
```
Select an option: 1
[2025-01-28 10:30:00] Starting system health check
[2025-01-28 10:30:00] WARNING: High disk usage: 85%
```

**Real-life Use Case:** Server management, user administration, system monitoring, backup automation.

**Cybersecurity Use Case:** Security configuration management, user access control, system hardening, audit preparation.

**Important Notes:** Always check for root privileges. Use proper logging. Validate user inputs. Implement error handling. Use absolute paths.

---

## Bash Scripting for Cybersecurity Automation
**One-line Definition:** Automate security tasks and monitoring using specialized bash scripts.

**Short Explanation:** Security automation scripts handle threat detection, log analysis, vulnerability scanning, and incident response tasks.

**Syntax:**
```bash
# Security commands
nmap -sS target
grep -i "error" /var/log/auth.log
```

**Example:**
```bash
#!/bin/bash
# Cybersecurity Automation Script

# Security configuration
readonly SECURITY_LOG="/var/log/security_monitor.log"
readonly ALERT_EMAIL="security@company.com"
readonly SUSPICIOUS_IPS="/tmp/suspicious_ips.txt"

# Security logging function
sec_log() {
    local level=$1
    shift
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] [SECURITY-$level] $*" | tee -a "$SECURITY_LOG"
}

# Detect suspicious login attempts
detect_suspicious_logins() {
    sec_log "INFO" "Starting suspicious login detection"
    
    # Find IPs with multiple failed logins
    grep "Failed password" /var/log/auth.log | \
    grep "$(date '+%b %d')" | \
    awk '{print $(NF-3)}' | \
    sort | uniq -c | sort -nr | \
    awk '$1 > 5 {print $2}' > "$SUSPICIOUS_IPS"
    
    if [ -s "$SUSPICIOUS_IPS" ]; then
        sec_log "ALERT" "Suspicious IPs detected:"
        while IFS= read -r ip; do
            sec_log "ALERT" "Multiple failed logins from: $ip"
            # Optional: Block IP using iptables
            # iptables -A INPUT -s "$ip" -j DROP
        done < "$SUSPICIOUS_IPS"
    else
        sec_log "INFO" "No suspicious login activity detected"
    fi
}

# Monitor open ports
monitor_open_ports() {
    sec_log "INFO" "Scanning open ports"
    
    # Get list of listening ports
    netstat -tuln | grep LISTEN | awk '{print $4}' | cut -d':' -f2 | sort -n > /tmp/open_ports.txt
    
    # Check for unusual ports
    local unusual_ports=$(comm -23 <(sort /tmp/open_ports.txt) <(echo -e "22\n80\n443\n25\n53"))
    
    if [ -n "$unusual_ports" ]; then
        sec_log "ALERT" "Unusual ports open: $unusual_ports"
    fi
}

# File integrity monitoring
monitor_file_integrity() {
    local checksum_file="/tmp/file_checksums.md5"
    local critical_files=("/etc/passwd" "/etc/shadow" "/etc/group" "/etc/hosts")
    
    sec_log "INFO" "Starting file integrity check"
    
    # Create checksums if they don't exist
    if [ ! -f "$checksum_file" ]; then
        for file in "${critical_files[@]}"; do
            if [ -f "$file" ]; then
                md5sum "$file" >> "$checksum_file"
            fi
        done
        sec_log "INFO" "Baseline checksums created"
        return
    fi
    
    # Check for changes
    for file in "${critical_files[@]}"; do
        if [ -f "$file" ]; then
            local current_md5=$(md5sum "$file" | awk '{print $1}')
            local stored_md5=$(grep "$file" "$checksum_file" | awk '{print $1}')
            
            if [ "$current_md5" != "$stored_md5" ]; then
                sec_log "ALERT" "File integrity violation: $file"
            fi
        fi
    done
}

# Automated security scan
security_scan() {
    local target=${1:-"localhost"}
    sec_log "INFO" "Starting security scan of: $target"
    
    # Port scan
    nmap -sS -O "$target" > "/tmp/scan_${target}_$(date +%Y%m%d).txt" 2>/dev/null
    sec_log "INFO" "Port scan completed for: $target"
    
    # Check for common vulnerabilities (simplified)
    if nmap --script vuln "$target" 2>/dev/null | grep -q "VULNERABLE"; then
        sec_log "ALERT" "Vulnerabilities found on: $target"
    fi
}

# Generate security report
generate_report() {
    local report_file="/tmp/security_report_$(date +%Y%m%d).txt"
    
    {
        echo "Security Report - $(date)"
        echo "========================"
        echo ""
        echo "System Information:"
        uname -a
        echo ""
        echo "Recent Security Events:"
        tail -20 "$SECURITY_LOG"
        echo ""
        echo "Current Users:"
        who
        echo ""
        echo "Network Connections:"
        netstat -tuln | head -10
    } > "$report_file"
    
    sec_log "INFO" "Security report generated: $report_file"
    
    # Email report (if mail command is available)
    if command -v mail >/dev/null; then
        mail -s "Security Report" "$ALERT_EMAIL" < "$report_file"
    fi
}

# Main security menu
security_menu() {
    PS3="Select security operation: "
    options=("Detect Suspicious Logins" "Monitor Open Ports" "File Integrity Check" 
             "Security Scan" "Generate Report" "Exit")
    
    select opt in "${options[@]}"; do
        case $opt in
            "Detect Suspicious Logins")
                detect_suspicious_logins
                ;;
            "Monitor Open Ports")
                monitor_open_ports
                ;;
            "File Integrity Check")
                monitor_file_integrity
                ;;
            "Security Scan")
                read -p "Enter target IP (default: localhost): " target
                security_scan "${target:-localhost}"
                ;;
            "Generate Report")
                generate_report
                ;;
            "Exit")
                sec_log "INFO" "Security monitoring tool exited"
                break
                ;;
            *)
                echo "Invalid option"
                ;;
        esac
    done
}

# Check dependencies
for cmd in nmap netstat md5sum; do
    if ! command -v "$cmd" >/dev/null; then
        echo "Required command not found: $cmd" >&2
        exit 1
    fi
done

# Check if running as root for some operations
if [ "$(id -u)" -ne 0 ]; then
    echo "Warning: Some operations require root privileges" >&2
fi

security_menu "$@"
```

**Output:**
```
Select security operation: 1
[2025-01-28 10:30:00] [SECURITY-INFO] Starting suspicious login detection
[2025-01-28 10:30:01] [SECURITY-ALERT] Suspicious IPs detected:
[2025-01-28 10:30:01] [SECURITY-ALERT] Multiple failed logins from: 192.168.1.100
```

**Real-life Use Case:** Security monitoring, threat detection, incident response automation.

**Cybersecurity Use Case:** SOC operations, penetration testing, vulnerability management, compliance monitoring.

**Important Notes:** Run with appropriate privileges. Log all security events. Validate inputs to prevent injection. Use secure communication channels. Regularly update security signatures.

---

# CYBERSECURITY SECTION

## Network Scanning Automation
**One-line Definition:** Automate network reconnaissance and vulnerability scanning using bash scripts.

**Short Explanation:** Network scanning automation involves creating scripts that perform port scans, service detection, and vulnerability assessments across multiple targets.

**Syntax:**
```bash
nmap -sS -p- target_ip
netstat -tuln
```

**Example:**
```bash
#!/bin/bash
# Network Scanning Automation Script

readonly SCAN_RESULTS="/tmp/network_scan_results.txt"
readonly TARGET_NETWORK="192.168.1.0/24"
readonly LOG_FILE="/var/log/network_scan.log"

# Network port scanning
network_port_scan() {
    local target=$1
    echo "[$(date)] Starting port scan on: $target" | tee -a "$LOG_FILE"
    
    # Quick scan of common ports
    nmap -sS -F "$target" >> "$SCAN_RESULTS" 2>&1
    
    # Full scan if quick scan finds open ports
    if grep -q "open" "$SCAN_RESULTS"; then
        echo "[$(date)] Open ports found on $target, performing full scan" | tee -a "$LOG_FILE"
        nmap -sS -p- -A "$target" >> "$SCAN_RESULTS" 2>&1
    fi
}

# Network discovery
network_discovery() {
    echo "[$(date)] Starting network discovery for: $TARGET_NETWORK" | tee -a "$LOG_FILE"
    
    # Ping sweep to find live hosts
    live_hosts=$(nmap -sn "$TARGET_NETWORK" | grep "Nmap scan report" | awk '{print $5}')
    
    for host in $live_hosts; do
        echo "[$(date)] Live host found: $host" | tee -a "$LOG_FILE"
        echo "=== Scan results for $host ===" >> "$SCAN_RESULTS"
        network_port_scan "$host"
        echo "" >> "$SCAN_RESULTS"
    done
}

network_discovery
echo "[$(date)] Network scanning completed" | tee -a "$LOG_FILE"
```

**Output:**
```
[2025-01-28 10:30:00] Starting network discovery for: 192.168.1.0/24
[2025-01-28 10:30:05] Live host found: 192.168.1.100
[2025-01-28 10:30:06] Starting port scan on: 192.168.1.100
```

**Real-life Use Case:** Network administrators monitoring infrastructure, security teams performing regular assessments.

**Cybersecurity Use Case:** Penetration testing, vulnerability assessments, network mapping for security audits.

**Important Notes:** Only scan networks you own or have permission to test. Use appropriate timing options to avoid network disruption.

---

## Log Monitoring
**One-line Definition:** Automate the analysis and monitoring of system and application logs for security events.

**Short Explanation:** Log monitoring scripts continuously analyze log files for suspicious patterns, security events, and system anomalies.

**Syntax:**
```bash
tail -f logfile | grep pattern
journalctl -f | grep error
```

**Example:**
```bash
#!/bin/bash
# Log Monitoring Script for Security

readonly LOG_MONITOR_LOG="/var/log/log_monitor.log"
readonly ALERT_THRESHOLD=5

# Alert function
send_alert() {
    local severity=$1
    local message=$2
    echo "[$(date)] [ALERT-$severity] $message" | tee -a "$LOG_MONITOR_LOG"
}

# Monitor authentication logs
monitor_auth_logs() {
    local auth_log="/var/log/auth.log"
    
    if [ ! -f "$auth_log" ]; then
        auth_log="/var/log/secure"  # RHEL/CentOS
    fi
    
    # Check for recent failed logins
    local failed_count=$(grep "$(date '+%b %d')" "$auth_log" | grep "Failed password" | wc -l)
    
    if [ $failed_count -gt $ALERT_THRESHOLD ]; then
        send_alert "HIGH" "Multiple failed login attempts detected: $failed_count"
        
        # Extract source IPs
        grep "$(date '+%b %d')" "$auth_log" | grep "Failed password" | \
        awk '{print $(NF-3)}' | sort | uniq -c | sort -nr
    fi
}

# Real-time log monitoring
realtime_monitor() {
    echo "Starting real-time log monitoring..."
    
    tail -f /var/log/auth.log 2>/dev/null | while read line; do
        if echo "$line" | grep -q "Failed password"; then
            send_alert "HIGH" "Failed login attempt: $(echo "$line" | awk '{print $(NF-3)}')"
        fi
        
        if echo "$line" | grep -q "ROOT LOGIN"; then
            send_alert "CRITICAL" "Root login detected: $line"
        fi
    done
}

monitor_auth_logs
echo "Log monitoring completed"
```

**Output:**
```
[2025-01-28 10:30:00] [ALERT-HIGH] Multiple failed login attempts detected: 8
192.168.1.100 5
192.168.1.101 3
```

**Real-life Use Case:** System administrators monitoring server health, security teams tracking suspicious activities.

**Cybersecurity Use Case:** SOC operations, incident response, compliance monitoring, threat hunting.

**Important Notes:** Ensure proper log file permissions. Configure log rotation to prevent disk overflow.

---

## Incident Response
**One-line Definition:** Automate initial incident response procedures using bash scripts for rapid threat containment.

**Short Explanation:** Incident response scripts provide automated actions for containing threats, preserving evidence, and initiating response procedures.

**Syntax:**
```bash
iptables -A INPUT -s ip -j DROP
kill -9 process_id
```

**Example:**
```bash
#!/bin/bash
# Incident Response Automation Script

readonly INCIDENT_LOG="/var/log/incident_response.log"
readonly EVIDENCE_DIR="/tmp/evidence_$(date +%Y%m%d_%H%M%S)"

# Incident logging function
ir_log() {
    local severity=$1
    shift
    echo "[$(date)] [INCIDENT-$severity] $*" | tee -a "$INCIDENT_LOG"
}

# Create evidence directory
create_evidence_dir() {
    mkdir -p "$EVIDENCE_DIR"
    chmod 700 "$EVIDENCE_DIR"
    ir_log "INFO" "Evidence directory created: $EVIDENCE_DIR"
}

# Isolate compromised system
isolate_system() {
    local target_ip=$1
    
    ir_log "CRITICAL" "Initiating system isolation for: $target_ip"
    
    if [ "$(id -u)" -eq 0 ]; then
        iptables -A INPUT -s "$target_ip" -j DROP
        iptables -A OUTPUT -d "$target_ip" -j DROP
        ir_log "CRITICAL" "Network isolation implemented for: $target_ip"
    else
        ir_log "ERROR" "Root privileges required for network isolation"
    fi
}

# Preserve system evidence
preserve_evidence() {
    local target_host=${1:-"localhost"}
    
    ir_log "INFO" "Preserving evidence from: $target_host"
    
    {
        echo "=== System Information ==="
        uname -a
        echo "=== Running Processes ==="
        ps aux
        echo "=== Network Connections ==="
        netstat -tuln
        echo "=== Active Users ==="
        who
    } > "$EVIDENCE_DIR/system_snapshot.txt"
    
    ir_log "INFO" "Evidence preservation completed"
}

# Kill suspicious processes
kill_suspicious_processes() {
    local process_name=$1
    
    ir_log "WARNING" "Terminating suspicious process: $process_name"
    
    local pids=$(pgrep -f "$process_name")
    
    if [ -n "$pids" ]; then
        for pid in $pids; do
            ps -p "$pid" -o pid,ppid,user,cmd > "$EVIDENCE_DIR/process_$pid.txt"
            kill -9 "$pid" 2>/dev/null
            ir_log "WARNING" "Process $pid ($process_name) terminated"
        done
    fi
}

create_evidence_dir
preserve_evidence
echo "Incident response procedures completed"
```

**Output:**
```
[2025-01-28 10:30:00] [INCIDENT-INFO] Evidence directory created: /tmp/evidence_20250128_103000
[2025-01-28 10:30:01] [INCIDENT-INFO] Preserving evidence from: localhost
[2025-01-28 10:30:02] [INCIDENT-INFO] Evidence preservation completed
```

**Real-life Use Case:** Security teams responding to security incidents, system administrators handling system compromises.

**Cybersecurity Use Case:** Incident response automation, malware containment, network isolation, evidence preservation.

**Important Notes:** Only use on systems you own or have explicit authorization. Document all actions for legal compliance.

---

## SOC Operations
**One-line Definition:** Automate Security Operations Center tasks using bash scripts for efficient security monitoring.

**Short Explanation:** SOC operations scripts help security analysts monitor multiple systems, analyze threats, and manage security incidents at scale.

**Syntax:**
```bash
collect_metrics
generate_dashboard
triage_alerts
```

**Example:**
```bash
#!/bin/bash
# SOC Operations Automation Script

readonly SOC_LOG="/var/log/soc_operations.log"
readonly DASHBOARD_FILE="/tmp/soc_dashboard.html"

# SOC logging function
soc_log() {
    local level=$1
    shift
    echo "[$(date)] [SOC-$level] $*" | tee -a "$SOC_LOG"
}

# Security metrics collection
collect_security_metrics() {
    soc_log "INFO" "Collecting security metrics"
    
    local failed_logins=$(grep "$(date '+%b %d')" /var/log/auth.log | grep "Failed password" | wc -l)
    local successful_logins=$(grep "$(date '+%b %d')" /var/log/auth.log | grep "Accepted" | wc -l)
    local open_ports=$(netstat -tuln | grep "LISTEN" | wc -l)
    
    echo "Failed Logins: $failed_logins"
    echo "Successful Logins: $successful_logins"
    echo "Open Ports: $open_ports"
    
    soc_log "INFO" "Metrics collection completed"
}

# Generate SOC dashboard
generate_dashboard() {
    soc_log "INFO" "Generating SOC dashboard"
    
    cat > "$DASHBOARD_FILE" << EOF
<!DOCTYPE html>
<html>
<head>
    <title>SOC Dashboard</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        .metric { background: white; padding: 20px; margin: 10px; border-radius: 8px; }
    </style>
</head>
<body>
    <h1>Security Operations Center Dashboard</h1>
    <p>Last updated: $(date)</p>
    <div class="metric">
        <h3>System Status</h3>
        <p>Load: $(uptime | awk -F'load average:' '{print $2}')</p>
        <p>Memory: $(free | awk 'NR==2{printf "%.1f%%", $3*100/$2}')</p>
        <p>Disk: $(df / | awk 'NR==2 {print $5}')</p>
    </div>
</body>
</html>
EOF
    
    soc_log "INFO" "Dashboard generated: $DASHBOARD_FILE"
}

# Security alert triage
triage_alerts() {
    soc_log "INFO" "Starting security alert triage"
    
    local failed_logins=$(grep "$(date '+%b %d')" /var/log/auth.log | grep "Failed password" | wc -l)
    local root_logins=$(grep "$(date '+%b %d')" /var/log/auth.log | grep "ROOT LOGIN" | wc -l)
    
    if [ $root_logins -gt 0 ]; then
        soc_log "CRITICAL" "Root login detected"
    fi
    
    if [ $failed_logins -gt 10 ]; then
        soc_log "HIGH" "High number of failed login attempts: $failed_logins"
    fi
}

collect_security_metrics
generate_dashboard
triage_alerts
echo "SOC operations completed"
```

**Output:**
```
Failed Logins: 3
Successful Logins: 15
Open Ports: 8
[2025-01-28 10:30:00] [SOC-INFO] Metrics collection completed
[2025-01-28 10:30:01] [SOC-INFO] Dashboard generated: /tmp/soc_dashboard.html
```

**Real-life Use Case:** Security operations centers, enterprise security teams, managed security service providers.

**Cybersecurity Use Case:** 24/7 security monitoring, threat intelligence analysis, incident coordination.

**Important Notes:** Ensure proper access to security logs. Configure secure communication channels for alerts.

---

## File Integrity Checking
**One-line Definition:** Monitor file system changes to detect unauthorized modifications using checksums.

**Short Explanation:** File integrity checking creates baseline checksums of critical files and monitors for changes that could indicate compromise.

**Syntax:**
```bash
md5sum file > checksums.md5
sha256sum file
```

**Example:**
```bash
#!/bin/bash
# File Integrity Monitoring System

readonly INTEGRITY_LOG="/var/log/file_integrity.log"
readonly BASELINE_FILE="/etc/file_baseline.md5"
readonly MONITOR_DIRS=("/etc" "/bin" "/sbin")

# Integrity logging function
integrity_log() {
    local level=$1
    shift
    echo "[$(date)] [INTEGRITY-$level] $*" | tee -a "$INTEGRITY_LOG"
}

# Create baseline checksums
create_baseline() {
    integrity_log "INFO" "Creating file integrity baseline"
    
    > "$BASELINE_FILE"
    
    for dir in "${MONITOR_DIRS[@]}"; do
        if [ -d "$dir" ]; then
            integrity_log "INFO" "Scanning directory: $dir"
            find "$dir" -type f -exec md5sum {} \; >> "$BASELINE_FILE" 2>/dev/null
        fi
    done
    
    chmod 600 "$BASELINE_FILE"
    integrity_log "INFO" "Baseline created with $(wc -l < "$BASELINE_FILE") files"
}

# Verify file integrity
verify_integrity() {
    if [ ! -f "$BASELINE_FILE" ]; then
        integrity_log "ERROR" "Baseline file not found: $BASELINE_FILE"
        return 1
    fi
    
    integrity_log "INFO" "Starting file integrity verification"
    
    local temp_baseline="/tmp/current_baseline.md5"
    > "$temp_baseline"
    
    for dir in "${MONITOR_DIRS[@]}"; do
        if [ -d "$dir" ]; then
            find "$dir" -type f -exec md5sum {} \; >> "$temp_baseline" 2>/dev/null
        fi
    done
    
    # Compare baselines
    local changes=$(diff "$BASELINE_FILE" "$temp_baseline")
    
    if [ -n "$changes" ]; then
        integrity_log "ALERT" "File integrity changes detected:"
        echo "$changes" | tee -a "$INTEGRITY_LOG"
    else
        integrity_log "INFO" "No file integrity changes detected"
    fi
    
    rm -f "$temp_baseline"
}

# Check specific file
check_file() {
    local file=$1
    
    if [ ! -f "$file" ]; then
        integrity_log "ERROR" "File not found: $file"
        return 1
    fi
    
    local current_md5=$(md5sum "$file" | awk '{print $1}')
    local stored_md5=$(grep "$file" "$BASELINE_FILE" 2>/dev/null | awk '{print $1}')
    
    if [ -z "$stored_md5" ]; then
        integrity_log "WARN" "New file detected: $file"
        echo "$current_md5  $file" >> "$BASELINE_FILE"
    elif [ "$current_md5" != "$stored_md5" ]; then
        integrity_log "ALERT" "File modified: $file"
        integrity_log "INFO" "Original MD5: $stored_md5"
        integrity_log "INFO" "Current MD5:  $current_md5"
    else
        integrity_log "INFO" "File integrity OK: $file"
    fi
}

# Main execution
case "${1:-}" in
    "create")
        create_baseline
        ;;
    "verify")
        verify_integrity
        ;;
    "check")
        if [ -n "${2:-}" ]; then
            check_file "$2"
        else
            echo "Usage: $0 check <file>"
            exit 1
        fi
        ;;
    *)
        echo "Usage: $0 {create|verify|check <file>}"
        exit 1
        ;;
esac
```

**Output:**
```
[2025-01-28 10:30:00] [INTEGRITY-INFO] Creating file integrity baseline
[2025-01-28 10:30:01] [INTEGRITY-INFO] Scanning directory: /etc
[2025-01-28 10:30:05] [INTEGRITY-INFO] Baseline created with 1250 files
```

**Real-life Use Case:** System administrators monitoring critical system files, compliance monitoring.

**Cybersecurity Use Case:** Intrusion detection, malware detection, compliance auditing, forensic analysis.

**Important Notes:** Store baseline files securely. Regularly update baselines after legitimate changes. Monitor the integrity monitoring system itself.

---

## Malware Analysis Automation (Theoretical)
**One-line Definition:** Automate preliminary malware analysis procedures using bash scripts for safe examination.

**Short Explanation:** Malware analysis automation scripts help perform static analysis and behavioral monitoring in controlled environments.

**Syntax:**
```bash
strings suspicious_file
hexdump -C suspicious_file
```

**Example:**
```bash
#!/bin/bash
# Malware Analysis Automation (Educational Only)

readonly ANALYSIS_DIR="/tmp/malware_analysis_$(date +%Y%m%d_%H%M%S)"
readonly ANALYSIS_LOG="/var/log/malware_analysis.log"

# Analysis logging function
analysis_log() {
    local level=$1
    shift
    echo "[$(date)] [MALWARE-$level] $*" | tee -a "$ANALYSIS_LOG"
}

# Create safe analysis environment
create_analysis_env() {
    mkdir -p "$ANALYSIS_DIR"
    chmod 700 "$ANALYSIS_DIR"
    
    # Create isolated network namespace (requires root)
    if [ "$(id -u)" -eq 0 ]; then
        unshare -n bash -c "echo 'Isolated network namespace created'"
    fi
    
    analysis_log "INFO" "Analysis environment created: $ANALYSIS_DIR"
}

# Static analysis
static_analysis() {
    local sample_file=$1
    
    if [ ! -f "$sample_file" ]; then
        analysis_log "ERROR" "Sample file not found: $sample_file"
        return 1
    fi
    
    analysis_log "INFO" "Starting static analysis of: $(basename "$sample_file")"
    
    # File information
    {
        echo "=== File Information ==="
        file "$sample_file"
        ls -la "$sample_file"
        echo ""
        
        echo "=== Hash Values ==="
        md5sum "$sample_file"
        sha256sum "$sample_file"
        echo ""
        
        echo "=== Strings Analysis ==="
        strings "$sample_file" | head -50
        echo ""
        
        echo "=== Hex Dump (first 256 bytes) ==="
        hexdump -C "$sample_file" | head -16
    } > "$ANALYSIS_DIR/static_analysis.txt"
    
    analysis_log "INFO" "Static analysis completed"
}

# Network behavior analysis
network_analysis() {
    local sample_file=$1
    
    analysis_log "INFO" "Starting network behavior analysis"
    
    # Monitor network connections during execution
    {
        echo "=== Network Monitoring ==="
        echo "Starting network capture..."
        
        # Start network monitoring
        tcpdump -i any -w "$ANALYSIS_DIR/network.pcap" &
        local tcpdump_pid=$!
        
        # Execute sample in isolated environment (simplified)
        timeout 30 "$sample_file" 2>/dev/null &
        local sample_pid=$!
        
        # Wait for execution or timeout
        sleep 35
        
        # Clean up
        kill $tcpdump_pid 2>/dev/null
        kill $sample_pid 2>/dev/null
        
        echo "Network capture completed"
    } > "$ANALYSIS_DIR/network_analysis.txt"
    
    analysis_log "INFO" "Network analysis completed"
}

# Generate analysis report
generate_report() {
    local sample_file=$1
    local report_file="/tmp/malware_report_$(date +%Y%m%d_%H%M%S).txt"
    
    {
        echo "Malware Analysis Report"
        echo "======================"
        echo "Sample: $(basename "$sample_file")"
        echo "Analysis Date: $(date)"
        echo "Analyst: $(whoami)"
        echo ""
        echo "WARNING: This analysis is for educational purposes only"
        echo ""
        echo "Static Analysis Results:"
        cat "$ANALYSIS_DIR/static_analysis.txt"
        echo ""
        echo "Network Analysis Results:"
        cat "$ANALYSIS_DIR/network_analysis.txt"
    } > "$report_file"
    
    analysis_log "INFO" "Analysis report generated: $report_file"
}

# Main analysis workflow
main() {
    echo "Malware Analysis Automation (Educational Only)"
    echo "=============================================="
    echo "WARNING: Only analyze files you own or have explicit permission to test"
    echo ""
    
    if [ -z "${1:-}" ]; then
        echo "Usage: $0 <sample_file>"
        exit 1
    fi
    
    local sample_file="$1"
    
    # Safety checks
    if [ ! -f "$sample_file" ]; then
        echo "Error: Sample file not found: $sample_file"
        exit 1
    fi
    
    echo "This tool is for educational purposes only."
    echo "Never analyze malicious software without proper training and containment."
    echo ""
    read -p "Continue with educational analysis? (y/N): " confirm
    
    if [[ $confirm != [yY] ]]; then
        echo "Analysis cancelled."
        exit 0
    fi
    
    create_analysis_env
    static_analysis "$sample_file"
    network_analysis "$sample_file"
    generate_report "$sample_file"
    
    echo "Educational analysis completed."
    echo "Analysis artifacts stored in: $ANALYSIS_DIR"
}

main "$@"
```

**Output:**
```
Malware Analysis Automation (Educational Only)
==============================================
WARNING: Only analyze files you own or have explicit permission to test

This tool is for educational purposes only.
Never analyze malicious software without proper training and containment.

Continue with educational analysis? (y/N): y
[2025-01-28 10:30:00] [MALWARE-INFO] Analysis environment created: /tmp/malware_analysis_20250128_103000
[2025-01-28 10:30:01] [MALWARE-INFO] Starting static analysis of: sample.exe
[2025-01-28 10:30:02] [MALWARE-INFO] Static analysis completed
Educational analysis completed.
```

**Real-life Use Case:** Security researchers studying malware, incident responders analyzing suspicious files.

**Cybersecurity Use Case:** Malware research, threat intelligence gathering, incident response, digital forensics.

**Important Notes:** Only analyze files you own or have explicit permission. Use proper containment and isolation. Never run unknown malware on production systems.

---

## Ethical Hacking Labs (TryHackMe / HTB – Legal Only)
**One-line Definition:** Automate ethical hacking lab setups and routine tasks using bash scripts for legal penetration testing.

**Short Explanation:** Ethical hacking scripts help set up lab environments, automate routine testing tasks, and manage penetration testing workflows legally.

**Syntax:**
```bash
setup_lab_environment
run_vulnerability_scan
generate_pentest_report
```

**Example:**
```bash
#!/bin/bash
# Ethical Hacking Lab Automation (Legal Only)

readonly LAB_LOG="/var/log/ethical_hacking_lab.log"
readonly LAB_DIR="/tmp/pentest_lab_$(date +%Y%m%d_%H%M%S)"

# Lab logging function
lab_log() {
    local level=$1
    shift
    echo "[$(date)] [LAB-$level] $*" | tee -a "$LAB_LOG"
}

# Legal disclaimer
show_disclaimer() {
    echo "=================================================="
    echo "ETHICAL HACKING LAB AUTOMATION - LEGAL USE ONLY"
    echo "=================================================="
    echo ""
    echo "This tool is for LEGAL ethical hacking purposes only."
    echo "Only use on systems you own or have explicit permission to test."
    echo "Unauthorized access to computer systems is illegal."
    echo ""
    echo "By continuing, you confirm:"
    echo "1. You have permission to test the target systems"
    echo "2. You are following all applicable laws and regulations"
    echo "3. You will use this knowledge responsibly"
    echo ""
}

# Setup lab environment
setup_lab() {
    local target_ip=${1:-"localhost"}
    
    lab_log "INFO" "Setting up ethical hacking lab for target: $target_ip"
    
    mkdir -p "$LAB_DIR"/{scans,exploits,reports,evidence}
    chmod 700 "$LAB_DIR"
    
    # Create lab configuration
    cat > "$LAB_DIR/lab_config.txt" << EOF
Target IP: $target_ip
Lab Created: $(date)
Analyst: $(whoami)
Purpose: Authorized penetration testing
EOF
    
    lab_log "INFO" "Lab environment created: $LAB_DIR"
}

# Reconnaissance phase
reconnaissance() {
    local target_ip=$1
    
    lab_log "INFO" "Starting reconnaissance phase for: $target_ip"
    
    {
        echo "=== Reconnaissance Results ==="
        echo "Target: $target_ip"
        echo "Date: $(date)"
        echo ""
        
        echo "=== Ping Test ==="
        ping -c 4 "$target_ip" 2>&1
        echo ""
        
        echo "=== Port Scan (Common Ports) ==="
        nmap -F "$target_ip" 2>&1
        echo ""
        
        echo "=== Service Version Detection ==="
        nmap -sV "$target_ip" 2>&1
        echo ""
        
        echo "=== OS Detection ==="
        nmap -O "$target_ip" 2>&1
    } > "$LAB_DIR/scans/reconnaissance.txt"
    
    lab_log "INFO" "Reconnaissance completed"
}

# Vulnerability scanning
vulnerability_scan() {
    local target_ip=$1
    
    lab_log "INFO" "Starting vulnerability scanning for: $target_ip"
    
    {
        echo "=== Vulnerability Scan Results ==="
        echo "Target: $target_ip"
        echo "Date: $(date)"
        echo ""
        
        echo "=== Full Port Scan ==="
        nmap -p- "$target_ip" 2>&1
        echo ""
        
        echo "=== Script Scan ==="
        nmap -sC "$target_ip" 2>&1
        echo ""
        
        echo "=== Safe Scripts ==="
        nmap --script safe "$target_ip" 2>&1
    } > "$LAB_DIR/scans/vulnerability_scan.txt"
    
    lab_log "INFO" "Vulnerability scanning completed"
}

# Web application testing
web_testing() {
    local target_ip=$1
    local target_port=${2:-80}
    
    lab_log "INFO" "Starting web application testing for: $target_ip:$target_port"
    
    {
        echo "=== Web Application Test Results ==="
        echo "Target: $target_ip:$target_port"
        echo "Date: $(date)"
        echo ""
        
        echo "=== HTTP Headers ==="
        curl -I "http://$target_ip:$target_port" 2>&1
        echo ""
        
        echo "=== Directory Enumeration (Common) ==="
        for dir in admin login test backup; do
            response=$(curl -s -o /dev/null -w "%{http_code}" "http://$target_ip:$target_port/$dir")
            echo "/$dir - HTTP $response"
        done
        echo ""
        
        echo "=== Technology Detection ==="
        curl -s "http://$target_ip:$target_port" | head -20
    } > "$LAB_DIR/scans/web_testing.txt"
    
    lab_log "INFO" "Web application testing completed"
}

# Generate penetration testing report
generate_pentest_report() {
    local target_ip=$1
    local report_file="/tmp/pentest_report_$(date +%Y%m%d_%H%M%S).txt"
    
    {
        echo "Penetration Testing Report"
        echo "=========================="
        echo "Target: $target_ip"
        echo "Date: $(date)"
        echo "Analyst: $(whoami)"
        echo "Purpose: Authorized security assessment"
        echo ""
        echo "Executive Summary:"
        echo "----------------"
        echo "This report contains the results of an authorized penetration test"
        echo "conducted on $target_ip. The assessment was performed using ethical"
        echo "hacking methodologies to identify potential security vulnerabilities."
        echo ""
        echo "Methodology:"
        echo "------------"
        echo "1. Reconnaissance - Information gathering and target analysis"
        echo "2. Scanning - Port scanning and service enumeration"
        echo "3. Vulnerability Assessment - Identification of security weaknesses"
        echo "4. Reporting - Documentation of findings and recommendations"
        echo ""
        echo "Findings:"
        echo "---------"
        
        # Summarize findings
        local open_ports=$(grep -c "open" "$LAB_DIR/scans/reconnaissance.txt" 2>/dev/null || echo "0")
        local vulnerabilities=$(grep -i "vulnerable\|cve" "$LAB_DIR/scans/vulnerability_scan.txt" 2>/dev/null | wc -l)
        
        echo "- Open ports discovered: $open_ports"
        echo "- Potential vulnerabilities identified: $vulnerabilities"
        echo ""
        
        echo "Detailed Results:"
        echo "----------------"
        echo "Reconnaissance Results:"
        cat "$LAB_DIR/scans/reconnaissance.txt" 2>/dev/null
        echo ""
        echo "Vulnerability Scan Results:"
        cat "$LAB_DIR/scans/vulnerability_scan.txt" 2>/dev/null
        echo ""
        echo "Web Testing Results:"
        cat "$LAB_DIR/scans/web_testing.txt" 2>/dev/null
        echo ""
        
        echo "Recommendations:"
        echo "---------------"
        echo "1. Close unnecessary open ports"
        echo "2. Update services to latest versions"
        echo "3. Implement proper access controls"
        echo "4. Regular security assessments"
        echo "5. Security awareness training"
        echo ""
        
        echo "Legal Notice:"
        echo "-------------"
        echo "This assessment was conducted with proper authorization."
        echo "All findings should be addressed in accordance with your"
        echo "organization's security policies and procedures."
    } > "$report_file"
    
    lab_log "INFO" "Penetration testing report generated: $report_file"
}

# Cleanup lab environment
cleanup_lab() {
    lab_log "INFO" "Cleaning up lab environment"
    
    # Archive lab results
    local archive="/tmp/pentest_lab_archive_$(date +%Y%m%d_%H%M%S).tar.gz"
    tar -czf "$archive" -C "$(dirname "$LAB_DIR")" "$(basename "$LAB_DIR")"
    
    # Remove sensitive files
    rm -rf "$LAB_DIR"
    
    lab_log "INFO" "Lab archived to: $archive"
    lab_log "INFO" "Lab cleanup completed"
}

# Main ethical hacking workflow
main() {
    show_disclaimer
    
    read -p "Do you understand and agree to these terms? (y/N): " consent
    if [[ $consent != [yY] ]]; then
        echo "Ethical hacking lab cancelled."
        exit 0
    fi
    
    if [ -z "${1:-}" ]; then
        echo "Usage: $0 <target_ip> [web_port]"
        exit 1
    fi
    
    local target_ip="$1"
    local web_port="${2:-80}"
    
    echo "Starting ethical hacking lab for: $target_ip"
    echo "This is for authorized testing only."
    echo ""
    
    setup_lab "$target_ip"
    reconnaissance "$target_ip"
    vulnerability_scan "$target_ip"
    web_testing "$target_ip" "$web_port"
    generate_pentest_report "$target_ip"
    
    echo ""
    echo "Ethical hacking lab completed."
    echo "All activities have been logged for accountability."
    echo ""
    read -p "Clean up lab environment? (y/N): " cleanup
    
    if [[ $cleanup == [yY] ]]; then
        cleanup_lab
    fi
    
    echo "Remember: Always obtain proper authorization before testing."
}

main "$@"
```

**Output:**
```
==================================================
ETHICAL HACKING LAB AUTOMATION - LEGAL USE ONLY
==================================================

This tool is for LEGAL ethical hacking purposes only.
Only use on systems you own or have explicit permission to test.
Unauthorized access to computer systems is illegal.

By continuing, you confirm:
1. You have permission to test the target systems
2. You are following all applicable laws and regulations
3. You will use this knowledge responsibly

Do you understand and agree to these terms? (y/N): y
Starting ethical hacking lab for: 192.168.1.100
This is for authorized testing only.

[2025-01-28 10:30:00] [LAB-INFO] Setting up ethical hacking lab for target: 192.168.1.100
[2025-01-28 10:30:01] [LAB-INFO] Lab environment created: /tmp/pentest_lab_20250128_103000
[2025-01-28 10:30:02] [LAB-INFO] Starting reconnaissance phase for: 192.168.1.100
Ethical hacking lab completed.
```

**Real-life Use Case:** Security professionals conducting authorized penetration tests, students learning ethical hacking.

**Cybersecurity Use Case:** Authorized penetration testing, vulnerability assessments, security audits, ethical hacking training.

**Important Notes:** Only use on systems you own or have explicit written permission. Follow all applicable laws and regulations. Document all testing activities.

---

## Process Substitution
**One-line Definition:** Use process output as temporary files without creating actual files.

**Short Explanation:** Process substitution allows treating command output as files using `<()` and `>()` syntax, enabling powerful data processing patterns.

**Syntax:**
```bash
command < <(another_command)    # Input from process
command > >(another_command)    # Output to process
diff <(cmd1) <(cmd2)            # Compare command outputs
```

**Example:**
```bash
#!/bin/bash
echo "Process Substitution Examples"
echo "============================"

# Compare two directories
echo "Comparing directory contents:"
diff <(ls -la /etc) <(ls -la /var) | head -5

# Read from process output
echo "Reading from process output:"
while read line; do
    echo "Found user: $line"
done < <(grep "/bin/bash" /etc/passwd | cut -d':' -f1)

# Multiple input streams
echo "Merging sorted outputs:"
sort -m <(echo -e "3\n1\n4") <(echo -e "2\n5\n6")

# Compress output on the fly
echo "Compressing output:"
tar -czf - /etc/hosts > >(gzip > hosts.tar.gz)
```

**Output:**
```
Process Substitution Examples
============================
Comparing directory contents:
Found user: root
Merging sorted outputs:
1
2
3
4
5
6
Compressing output:
```

**Real-life Use Case:** Compare command outputs, process streaming data, create temporary data pipelines.

**Cybersecurity Use Case:** Compare system snapshots, analyze log differences, process security data streams.

**Important Notes:** Process substitution creates temporary files in `/dev/fd`. Not available in very old shell versions.

---

## Here Documents and Here Strings
**One-line Definition:** Create multi-line input within scripts using redirection syntax.

**Short Explanation:** Here documents (`<<`) allow embedding multi-line text, while here strings (`<<<`) provide single-line string input.

**Syntax:**
```bash
<<EOF        # Here document start
content
EOF          # Here document end

<<<"string"  # Here string
```

**Example:**
```bash
#!/bin/bash
echo "Here Documents and Strings"
echo "=========================="

# Here document for multi-line text
cat << 'EOF' > config.txt
[Database]
host=localhost
port=3306
username=admin
password=secret
EOF

echo "Config file created:"
cat config.txt

# Here string for single input
echo "Here string example:"
grep "host" <<< "host=localhost port=3306"

# Variable substitution in here document
name="Alice"
age=25
cat << EOF
User Profile
============
Name: $name
Age: $age
Date: $(date)
EOF

# Piped here document
echo "Creating script with here document:"
cat > script.sh << 'EOS'
#!/bin/bash
echo "Generated script"
echo "Current time: $(date)"
EOS

chmod +x script.sh
./script.sh
```

**Output:**
```
Here Documents and Strings
==========================
Config file created:
[Database]
host=localhost
port=3306
username=admin
password=secret
Here string example:
host=localhost
User Profile
============
Name: Alice
Age: 25
Date: Tue Jan 28 10:30:00 EST 2025
Generated script
Current time: Tue Jan 28 10:30:00 EST 2025
```

**Real-life Use Case:** Generate configuration files, create scripts, embed documentation.

**Cybersecurity Use Case:** Generate security configs, create incident reports, embed encrypted data.

**Important Notes:** Quote EOF (`'EOF'`) to prevent variable expansion. Use `-` for indentation stripping.

---

## Coprocesses
**One-line Definition:** Run background processes that can communicate bidirectionally with the main script.

**Short Explanation:** Coprocesses enable two-way communication between a script and background process using file descriptors.

**Syntax:**
```bash
coproc command_name         # Start coprocess
echo "data" >&${command_name[1]}  # Send input
read result <&${command_name[0]}   # Read output
```

**Example:**
```bash
#!/bin/bash
echo "Coprocess Examples"
echo "=================="

# Start a coprocess with bc calculator
coproc BC { bc; }

# Send calculations and read results
echo "scale=2; 10/3" >&${BC[1]}
read result <&${BC[0]}
echo "10/3 = $result"

echo "scale=4; 22/7" >&${BC[1]}
read result <&${BC[0]}
echo "22/7 = $result"

# Interactive coprocess
coproc AWK { awk '{print "Line " NR ": " toupper($0)}'; }

echo "hello world" >&${AWK[1]}
read output <&${AWK[0]}
echo "AWK output: $output"

echo "bash scripting" >&${AWK[1]}
read output <&${AWK[0]}
echo "AWK output: $output"

# Close coprocesses
kill $BC_PID $AWK_PID 2>/dev/null
```

**Output:**
```
Coprocess Examples
==================
10/3 = 3.33
22/7 = 3.1428
AWK output: Line 1: HELLO WORLD
AWK output: Line 2: BASH SCRIPTING
```

**Real-life Use Case:** Interactive data processing, background calculations, persistent connections.

**Cybersecurity Use Case:** Real-time log analysis, interactive security tools, persistent monitoring connections.

**Important Notes:** Coprocesses require Bash 4+. Use proper file descriptor management. Always clean up coprocesses.

---

## Extended Globbing
**One-line Definition:** Use advanced pattern matching for more powerful file selection.

**Short Explanation:** Extended globbing provides sophisticated pattern matching beyond standard wildcards using operators like `?()`, `*()`, `+()`, and `@()`.

**Syntax:**
```bash
shopt -s extglob           # Enable extended globbing
?(pattern)    # Zero or one occurrence
*(pattern)    # Zero or more occurrences
+(pattern)    # One or more occurrences
@(pattern)    # Exact match
!(pattern)    # Negation (anything except)
```

**Example:**
```bash
#!/bin/bash
echo "Extended Globbing Examples"
echo "=========================="

# Enable extended globbing
shopt -s extglob

# Create test files
touch file1.txt file2.txt file10.txt file.log file.backup image.jpg

# Pattern matching examples
echo "Files ending with .txt:"
ls -la *.txt

echo "Files starting with 'file' and ending with digit:"
ls -la file+([0-9]).txt

echo "Files with exactly 3 characters:"
ls -la ???.*

echo "Files not ending in .txt:"
ls -la !(*.txt)

echo "Files ending in .log or .backup:"
ls -la *.@(log|backup)

echo "Files starting with 'file' (zero or more digits):"
ls -la file*([0-9]).*

# Complex pattern matching
echo "Complex pattern - files starting with 'f', ending with digit or .log:"
ls -la f*([0-9]).@(txt|log)

# Disable extended globbing
shopt -u extglob

# Clean up
rm -f file1.txt file2.txt file10.txt file.log file.backup image.jpg
```

**Output:**
```
Extended Globbing Examples
==========================
Files ending with .txt:
file1.txt  file10.txt  file2.txt
Files starting with 'file' and ending with digit:
file1.txt  file10.txt  file2.txt
Files with exactly 3 characters:
Files not ending in .txt:
file.backup  file.log  image.jpg
Files ending in .log or .backup:
file.backup  file.log
Files starting with 'file' (zero or more digits):
file1.txt  file10.txt  file2.txt  file.log
Complex pattern - files starting with 'f', ending with digit or .log:
file1.txt  file10.txt  file2.txt  file.log
```

**Real-life Use Case:** Complex file selection, backup filtering, log file management.

**Cybersecurity Use Case:** Pattern-based malware detection, log file filtering, suspicious file identification.

**Important Notes:** Must enable with `shopt -s extglob`. Patterns are case-sensitive. Can be combined with standard globbing.

---

## Brace Expansion
**One-line Definition:** Generate multiple strings from patterns using curly braces.

**Short Explanation:** Brace expansion creates multiple strings by combining elements within braces, useful for generating file names, directories, or command sequences.

**Syntax:**
```bash
{a,b,c}      # Multiple options
{1..5}       # Number range
{a..z}       # Letter range
{prefix,}{suffix}  # Combinations
```

**Example:**
```bash
#!/bin/bash
echo "Brace Expansion Examples"
echo "========================"

# Simple expansion
echo "Simple expansion:"
echo {red,green,blue}
echo file.{txt,log,bak}

# Number ranges
echo "Number ranges:"
echo {1..5}
echo image_{001..003}.jpg

# Letter ranges
echo "Letter ranges:"
echo {a..e}
echo section_{A..C}

# Nested expansion
echo "Nested expansion:"
echo {user,admin}_{read,write,execute}
echo backup_{202{3..5}}_{01..03}

# Command generation
echo "Command generation:"
for i in {1..3}; do
    echo "Processing item $i"
done

# Directory creation
echo "Directory creation:"
mkdir -p project/{src,docs,tests}/{main,backup}
echo "Created project structure"

# File operations
echo "File operations:"
touch report_{jan,feb,mar}.txt
ls -la report_*.txt

# Complex combinations
echo "Complex combinations:"
echo server_{prod,test}_{db,web}_{1..2}

# Clean up
rm -rf project report_*.txt
```

**Output:**
```
Brace Expansion Examples
========================
Simple expansion:
red green blue
file.txt file.log file.bak
Number ranges:
1 2 3 4 5
image_001.jpg image_002.jpg image_003.jpg
Letter ranges:
a b c d e
section_A section_B section_C
Nested expansion:
user_read user_write user_execute admin_read admin_write admin_execute
backup_2023_01 backup_2023_02 backup_2023_03 backup_2024_01 backup_2024_02 backup_2024_03 backup_2025_01 backup_2025_02 backup_2025_03
Command generation:
Processing item 1
Processing item 2
Processing item 3
Directory creation:
Created project structure
File operations:
-rw-r--r-- 1 user user 0 Jan 28 10:30 report_feb.txt
-rw-r--r-- 1 user user 0 Jan 28 10:30 report_jan.txt
-rw-r--r-- 1 user user 0 Jan 28 10:30 report_mar.txt
Complex combinations:
server_prod_db_1 server_prod_db_2 server_prod_web_1 server_prod_web_2 server_test_db_1 server_test_db_2 server_test_web_1 server_test_web_2
```

**Real-life Use Case:** Batch file operations, directory structure creation, command generation.

**Cybersecurity Use Case:** Generate test cases, create security scan targets, batch process security files.

**Important Notes:** Expansion happens before other shell expansions. Use quotes to prevent expansion when needed.

---

## Named Pipes (FIFOs)
**One-line Definition:** Create special files that allow inter-process communication.

**Short Explanation:** Named pipes (FIFOs) enable communication between unrelated processes by creating a special file that acts as a pipe.

**Syntax:**
```bash
mkfifo pipe_name        # Create named pipe
echo "data" > pipe_name  # Write to pipe
cat < pipe_name         # Read from pipe
```

**Example:**
```bash
#!/bin/bash
echo "Named Pipe (FIFO) Examples"
echo "=========================="

# Create named pipe
PIPE_FILE="/tmp/my_pipe"
mkfifo "$PIPE_FILE"

echo "Named pipe created: $PIPE_FILE"

# Producer process (background)
{
    echo "Producer: Starting data generation"
    for i in {1..5}; do
        echo "Message $i" > "$PIPE_FILE"
        echo "Producer: Sent message $i"
        sleep 1
    done
    echo "Producer: Finished"
} &

PRODUCER_PID=$!

# Consumer process
{
    echo "Consumer: Starting to read from pipe"
    while IFS= read -r line; do
        echo "Consumer: Received - $line"
    done < "$PIPE_FILE"
    echo "Consumer: Pipe closed, exiting"
} &

CONSUMER_PID=$!

# Wait for both processes
wait $PRODUCER_PID
wait $CONSUMER_PID

# Multiple readers example
echo -e "\nMultiple readers example:"
mkfifo /tmp/multi_pipe

# Multiple consumers
for i in {1..3}; do
    {
        echo "Reader $i: Starting"
        while IFS= read -r line; do
            echo "Reader $i: Got $line"
            break
        done < /tmp/multi_pipe
        echo "Reader $i: Finished"
    } &
done

# Single producer
{
    sleep 1
    echo "Broadcast message" > /tmp/multi_pipe
} &

wait

# Clean up
rm -f "$PIPE_FILE" /tmp/multi_pipe
echo "Named pipes cleaned up"
```

**Output:**
```
Named Pipe (FIFO) Examples
==========================
Named pipe created: /tmp/my_pipe
Producer: Starting data generation
Consumer: Starting to read from pipe
Producer: Sent message 1
Consumer: Received - Message 1
Producer: Sent message 2
Consumer: Received - Message 2
Producer: Sent message 3
Consumer: Received - Message 3
Producer: Sent message 4
Consumer: Received - Message 4
Producer: Sent message 5
Consumer: Received - Message 5
Producer: Finished
Consumer: Pipe closed, exiting

Multiple readers example:
Reader 1: Starting
Reader 2: Starting
Reader 3: Starting
Reader 1: Got Broadcast message
Reader 1: Finished
Reader 2: Got Broadcast message
Reader 2: Finished
Reader 3: Got Broadcast message
Reader 3: Finished
Named pipes cleaned up
```

**Real-life Use Case:** Inter-process communication, data pipelines, concurrent processing.

**Cybersecurity Use Case:** Real-time log monitoring, security event distribution, coordinated security tools.

**Important Notes:** Named pipes block on read until data is available. Use background processes for non-blocking behavior. Clean up pipes after use.

---

## Mathematical Operations with bc
**One-line Definition:** Perform advanced mathematical calculations using the bc calculator.

**Short Explanation:** The `bc` command provides arbitrary-precision arithmetic and supports advanced mathematical functions beyond bash's built-in integer arithmetic.

**Syntax:**
```bash
echo "expression" | bc          # Basic calculation
bc <<< "expression"             # Here string
bc -l <<< "expression"          # Math library
scale=n                         # Set decimal places
```

**Example:**
```bash
#!/bin/bash
echo "Mathematical Operations with bc"
echo "=============================="

# Basic arithmetic with floating point
echo "Basic floating point arithmetic:"
echo "scale=2; 10/3" | bc
echo "scale=4; 22/7" | bc

# Square root
echo "Square root:"
echo "scale=6; sqrt(16)" | bc -l
echo "scale=6; sqrt(2)" | bc -l

# Power function
echo "Power calculations:"
echo "scale=4; 2^10" | bc -l
echo "scale=4; 3^4" | bc -l

# Trigonometric functions (using math library)
echo "Trigonometric functions:"
echo "scale=6; s(3.14159/2)" | bc -l  # sine
echo "scale=6; c(3.14159)" | bc -l     # cosine
echo "scale=6; a(1)" | bc -l          # arctangent

# Complex calculations
echo "Complex calculations:"
echo "scale=8; (sqrt(5) + 1) / 2" | bc -l  # Golden ratio
echo "scale=4; 9 * 5 / (3 + 2)" | bc -l

# Financial calculations
echo "Financial calculations:"
principal=1000
rate=0.05
years=3
amount=$(echo "scale=2; $principal * (1 + $rate)^$years" | bc -l)
echo "Compound interest: $amount"

# Scientific notation
echo "Scientific notation:"
echo "scale=10; 1.23e6 * 4.56e-3" | bc -l

# Comparison operations
echo "Comparison operations:"
result=$(echo "10 > 5" | bc)
echo "10 > 5: $result"

result=$(echo "5 == 10" | bc)
echo "5 == 10: $result"

# Custom function in bc
echo "Custom function:"
echo "
define factorial(n) {
    if (n <= 1) return 1
    return n * factorial(n-1)
}
factorial(5)
" | bc
```

**Output:**
```
Mathematical Operations with bc
==============================
Basic floating point arithmetic:
3.33
3.1428
Square root:
4.000000
1.414213
Power calculations:
1024.0000
81.0000
Trigonometric functions:
1.000000
-1.000000
.785398
Complex calculations:
1.61803398
9.0000
Financial calculations:
Compound interest: 1157.62
Scientific notation:
5608.8000000000
Comparison operations:
10 > 5: 1
5 == 10: 0
Custom function:
120
```

**Real-life Use Case:** Financial calculations, scientific computing, engineering computations.

**Cybersecurity Use Case:** Cryptographic calculations, risk assessment scoring, statistical analysis of security data.

**Important Notes:** Use `bc -l` for math library functions. Set appropriate scale for precision. Use quotes for complex expressions.

---

# 📚 BASH SCRIPTING REFERENCE - KEYWORDS, FUNCTIONS & VARIABLES

## 📋 QUICK INDEX

### **🔤 ALPHABETICAL INDEX:**
- **[A]** - [Arrays](#-array-operations), [Arithmetic Operators](#-arithmetic-operators), [alias](#-built-in-functions--commands), [awk](#-built-in-functions--commands)
- **[B]** - [break](#-essential-bash-keywords), [basename](#-built-in-functions--commands), [bg](#-built-in-functions--commands), [brace expansion](#-pattern-matching)
- **[C]** - [case](#-essential-bash-keywords), [continue](#-essential-bash-keywords), [cd](#-built-in-functions--commands), [chmod](#-built-in-functions--commands), [cp](#-built-in-functions--commands), [cut](#-built-in-functions--commands)
- **[D]** - [do](#-essential-bash-keywords), [done](#-essential-bash-keywords), [dirname](#-built-in-functions--commands), [date](#-built-in-functions--commands), [df](#-built-in-functions--commands), [du](#-built-in-functions--commands)
- **[E]** - [else](#-essential-bash-keywords), [elif](#-essential-bash-keywords), [esac](#-essential-bash-keywords), [exit](#-essential-bash-keywords), [exec](#-built-in-functions--commands), [export](#-built-in-functions--commands), [echo](#-built-in-functions--commands)
- **[F]** - [for](#-essential-bash-keywords), [fi](#-essential-bash-keywords), [find](#-built-in-functions--commands), [fg](#-built-in-functions--commands), [file functions](#-file-functions)
- **[G]** - [grep](#-built-in-functions--commands), [globbing](#-pattern-matching), [group operations](#-logical-operators)
- **[H]** - [here document](#redirection-keywords), [here string](#redirection-keywords), [head](#-built-in-functions--commands)
- **[I]** - [if](#-essential-bash-keywords), [in](#-essential-bash-keywords), [IFS](#-special-variables), [id](#-built-in-functions--commands)
- **[J]** - [jobs](#-built-in-functions--commands), [job control](#-job-control)
- **[K]** - [kill](#-built-in-functions--commands), [killall](#-built-in-functions--commands)
- **[L]** - [ls](#-built-in-functions--commands), [logical operators](#-logical-operators), [loop control](#-essential-bash-keywords)
- **[M]** - [mkdir](#-built-in-functions--commands), [mv](#-built-in-functions--commands), [man](#-built-in-functions--commands)
- **[N]** - [not](#-logical-operators), [nohup](#-job-control)
- **[O]** - [operators](#-arithmetic-operators), [options](#-shell-options)
- **[P]** - [pipe](#-redirection-keywords), [ps](#-built-in-functions--commands), [pwd](#-built-in-functions--commands), [printf](#-built-in-functions--commands), [pattern matching](#-pattern-matching)
- **[Q]** - [quotes](#-quote-types), [quiet mode](#-shell-options)
- **[R]** - [return](#-essential-bash-keywords), [read](#-built-in-functions--commands), [rm](#-built-in-functions--commands), [redirection](#-redirection-keywords)
- **[S]** - [signals](#-signals), [sort](#-built-in-functions--commands), [sed](#-built-in-functions--commands), [sleep](#-built-in-functions--commands), [source](#-built-in-functions--commands), [string operations](#-string-operations), [system functions](#-system-functions)
- **[T]** - [then](#-essential-bash-keywords), [test](#-test-operators), [touch](#-built-in-functions--commands), [tr](#-built-in-functions--commands), [type](#-built-in-functions--commands)
- **[U]** - [until](#-essential-bash-keywords), [unset](#-built-in-functions--commands), [user functions](#-built-in-functions--commands)
- **[V]** - [variables](#-special-variables), [validation](#-test-operators)
- **[W]** - [while](#-essential-bash-keywords), [wc](#-built-in-functions--commands), [which](#-built-in-functions--commands), [wildcards](#-pattern-matching)
- **[X]** - [exec](#-built-in-functions--commands), [export](#-built-in-functions--commands)
- **[Y]** - [yes](#-built-in-functions--commands)
- **[Z]** - [zenity](#-built-in-functions--commands), [zsh](#-shell-options)

### **📂 CATEGORY INDEX:**
- **[Control Flow]** - [if/else/fi](#-essential-bash-keywords), [case/esac](#-essential-bash-keywords), [for/do/done](#-essential-bash-keywords), [while/do/done](#-essential-bash-keywords), [until/do/done](#-essential-bash-keywords)
- **[Data Types]** - [Strings](#-string-operations), [Arrays](#-array-operations), [Numbers](#-arithmetic-operators), [Files](#-file-functions)
- **[File Operations]** - [File I/O](#-file-functions), [Redirection](#-redirection-keywords), [Permissions](#-built-in-functions--commands)
- **[Process Management]** - [Background Jobs](#-job-control), [Signals](#-signals), [Process Control](#-system-functions)
- **[Text Processing]** - [String Functions](#-string-functions), [Pattern Matching](#-pattern-matching), [Text Filters](#-built-in-functions--commands)
- **[System Administration]** - [User Management](#-system-functions), [System Info](#-system-functions), [Environment](#-special-variables)
- **[Security]** - [Permissions](#-built-in-functions--commands), [Validation](#-test-operators), [Secure Scripting](#-shell-options)

### **🎯 SKILL LEVEL INDEX:**
- **[Beginner]** - [Basic Keywords](#-essential-bash-keywords), [Simple Variables](#-special-variables), [Basic Commands](#-built-in-functions--commands)
- **[Intermediate]** - [Arrays](#-array-operations), [String Operations](#-string-operations), [Redirection](#-redirection-keywords)
- **[Advanced]** - [Process Control](#-job-control), [Signals](#-signals), [Pattern Matching](#-pattern-matching)
- **[Expert]** - [Shell Options](#-shell-options), [Advanced Operators](#-arithmetic-operators), [Complex Operations](#-string-operations)

### **🔍 SEARCH INDEX:**
- **[Conditional Logic]** - [if](#-essential-bash-keywords), [test](#-test-operators), [logical operators](#-logical-operators)
- **[Loops & Iteration]** - [for](#-essential-bash-keywords), [while](#-essential-bash-keywords), [until](#-essential-bash-keywords), [break](#-essential-bash-keywords), [continue](#-essential-bash-keywords)
- **[Data Manipulation]** - [strings](#-string-operations), [arrays](#-array-operations), [arithmetic](#-arithmetic-operators)
- **[File System]** - [file operations](#-file-functions), [directory operations](#-built-in-functions--commands), [permissions](#-built-in-functions--commands)
- **[Process & System]** - [process management](#-job-control), [system information](#-system-functions), [environment](#-special-variables)

---

## 🔑 ESSENTIAL BASH KEYWORDS

### **Control Flow Keywords:**
- **`if`** - Start conditional block to test conditions and execute code based on true/false results
- **`then`** - Execute commands when the preceding `if` condition is true
- **`else`** - Execute commands when the preceding `if` condition is false
- **`elif`** - Additional conditional test when previous `if` conditions were false
- **`fi`** - End conditional block (reverse of `if`)
- **`case`** - Start multi-way conditional for pattern matching against multiple values
- **`in`** - Specify pattern list in `case` statement or iterate over items in `for` loop
- **`esac`** - End case statement (reverse of `case`)
- **`for`** - Loop through items in a list or range of values
- **`while`** - Loop continuously while a condition remains true
- **`until`** - Loop continuously until a condition becomes true
- **`do`** - Start loop body where commands are executed
- **`done`** - End loop block
- **`break`** - Exit from current loop immediately
- **`continue`** - Skip current iteration and continue with next loop iteration
- **`return`** - Exit from function and optionally return a value
- **`exit`** - Exit from script with optional exit status code

### **Redirection Keywords:**
- **`>`** - Redirect output to file, overwriting existing content
- **`>>`** - Redirect output to file, appending to existing content
- **`<`** - Redirect input from file to command
- **`<<`** - Here document - read multi-line input until delimiter
- **`<<<`** - Here string - pass single string as input to command
- **`2>`** - Redirect stderr (error output) to file
- **`&>`** - Redirect both stdout and stderr to file
- **`|`** - Pipe - send output of one command as input to another

### **Test Operators:**
- **`[`** - Start test expression for conditional evaluation (alias of `test`)
- **`[[`** - Start extended test expression with advanced pattern matching
- **`((`** - Start arithmetic evaluation for integer calculations
- **`-eq`** - Numeric equality test (equals)
- **`-ne`** - Numeric inequality test (not equals)
- **`-lt`** - Numeric less than test
- **`-gt`** - Numeric greater than test
- **`==`** - String equality test
- **`!=`** - String inequality test
- **`=~`** - Regular expression pattern match test
- **`-z`** - Test if string is empty (zero length)
- **`-n`** - Test if string is not empty (non-zero length)
- **`-f`** - Test if file exists and is regular file
- **`-d`** - Test if directory exists
- **`-r`** - Test if file is readable
- **`-w`** - Test if file is writable
- **`-x`** - Test if file is executable

---

## 🛠️ BUILT-IN FUNCTIONS & COMMANDS

### **String Functions:**
- **`echo`** - Display text or variables to standard output
- **`printf`** - Format and display text with advanced formatting options
- **`read`** - Read input from user or file into variables
- **`basename`** - Extract filename from full path
- **`dirname`** - Extract directory path from full path
- **`tr`** - Translate or delete characters from input stream
- **`sed`** - Stream editor for text transformation
- **`awk`** - Pattern scanning and text processing language
- **`cut`** - Extract columns/fields from input lines
- **`sort`** - Sort lines of text files
- **`uniq`** - Remove duplicate lines from sorted input
- **`grep`** - Search for patterns in text using regular expressions
- **`wc`** - Count lines, words, and characters in input

### **File Functions:**
- **`touch`** - Create empty files or update file timestamps
- **`mkdir`** - Create directories
- **`rm`** - Remove files or directories
- **`cp`** - Copy files or directories
- **`mv`** - Move or rename files and directories
- **`find`** - Search for files and directories based on criteria
- **`ls`** - List directory contents
- **`cd`** - Change current working directory
- **`pwd`** - Print current working directory
- **`chmod`** - Change file permissions
- **`chown`** - Change file ownership
- **`stat`** - Display file or filesystem status

### **System Functions:**
- **`ps`** - Display running processes
- **`kill`** - Send signals to processes
- **`killall`** - Kill processes by name
- **`sleep`** - Pause execution for specified time
- **`date`** - Display or set system date and time
- **`whoami`** - Display current username
- **`id`** - Display user and group information
- **`which`** - Locate command in PATH
- **`type`** - Display command type and location
- **`export`** - Set environment variables
- **`unset`** - Remove variables or functions
- **`alias`** - Create command aliases
- **`unalias`** - Remove command aliases
- **`source`** - Execute commands from file in current shell
- **`exec`** - Replace current shell with new command
- **`wait`** - Wait for background jobs to complete
- **`jobs`** - Display active background jobs
- **`bg`** - Resume suspended job in background
- **`fg`** - Resume suspended job in foreground

---

## 📊 SPECIAL VARIABLES

### **Positional Parameters:**
- **`$0`** - Script name or command being executed
- **`$1, $2, $3...`** - Positional parameters (arguments to script)
- **`$#`** - Number of positional parameters
- **`$*`** - All positional parameters as single string
- **`$@`** - All positional parameters as separate strings

### **Process Variables:**
- **`$?`** - Exit status of last command (0=success, non-zero=failure)
- **`$$`** - Process ID (PID) of current shell
- **`$!`** - Process ID (PID) of most recent background command
- **`$-`** - Current shell options
- **`$_`** - Last argument of previous command

### **Environment Variables:**
- **`$HOME`** - Current user's home directory
- **`$PATH`** - Search path for commands
- **`$USER`** - Current username
- **`$SHELL`** - Current shell path
- **`$PWD`** - Current working directory
- **`$OLDPWD`** - Previous working directory
- **`$RANDOM`** - Random number between 0-32767
- **`$SECONDS`** - Number of seconds since script started
- **`$IFS`** - Internal Field Separator (default: space, tab, newline)

---

## 🎯 ARITHMETIC OPERATORS

### **Basic Operators:**
- **`$((expression))`** - Arithmetic evaluation
- **`+`** - Addition
- **`-`** - Subtraction
- **`*`** - Multiplication
- **`/`** - Integer division
- **`%`** - Modulo (remainder)
- **`**`** - Exponentiation

### **Assignment Operators:**
- **`++`** - Increment
- **`--`** - Decrement
- **`+=`** - Add and assign
- **`-=`** - Subtract and assign
- **`*=`** - Multiply and assign
- **`/=`** - Divide and assign

---

## 📝 STRING OPERATIONS

### **Variable Expansion:**
- **`$variable`** - Variable value expansion
- **`${variable}`** - Variable expansion with braces
- **`${variable:position}`** - Substring from position
- **`${variable:position:length}`** - Substring with length

### **Pattern Matching:**
- **`${variable#pattern}`** - Remove shortest prefix pattern
- **`${variable##pattern}`** - Remove longest prefix pattern
- **`${variable%pattern}`** - Remove shortest suffix pattern
- **`${variable%%pattern}`** - Remove longest suffix pattern

### **Replacement & Case:**
- **`${variable/pattern/replacement}`** - Replace first occurrence
- **`${variable//pattern/replacement}`** - Replace all occurrences
- **`${variable^pattern}`** - Uppercase first character
- **`${variable^^pattern}`** - Uppercase all characters
- **`${variable,pattern}`** - Lowercase first character
- **`${variable,,pattern}`** - Lowercase all characters

---

## 🔧 ARRAY OPERATIONS

### **Array Access:**
- **`${array[index]}`** - Access array element by index
- **`${array[@]}`** - All array elements as separate words
- **`${array[*]}`** - All array elements as single string
- **`${#array[@]}`** - Number of array elements
- **`${!array[@]}`** - All array indices

### **Array Manipulation:**
- **`array=(value1 value2)`** - Declare array with values
- **`array[index]=value`** - Set array element value
- **`unset array[index]`** - Remove array element

---

## 🚀 LOGICAL OPERATORS

### **Command Chaining:**
- **`&&`** - Logical AND (execute second command if first succeeds)
- **`||`** - Logical OR (execute second command if first fails)
- **`!`** - Logical NOT (negate exit status)

### **Test Expression Operators:**
- **`-a`** - Logical AND in test expressions
- **`-o`** - Logical OR in test expressions

---

## 📋 QUOTE TYPES

### **Single Quotes:**
- **`'text'`** - Single quotes (literal text, no expansion)

### **Double Quotes:**
- **`"text"`** - Double quotes (variable and command expansion)

### **Command Substitution:**
- **`` `command` `` - Backticks (command substitution, old style)
- **`$(command)`** - Command substitution (preferred style)

---

## 🎮 JOB CONTROL

### **Background Operations:**
- **`&`** - Run command in background
- **`Ctrl+C`** - Interrupt/kill current foreground process
- **`Ctrl+Z`** - Suspend current foreground process
- **`nohup`** - Run command immune to hangups
- **`disown`** - Remove job from shell's job table

---

## 🔍 PATTERN MATCHING

### **Wildcards:**
- **`*`** - Match any string (including empty)
- **`?`** - Match exactly one character
- **`[abc]`** - Match any character in brackets
- **`[a-z]`** - Match any character in range
- **`[!abc]`** - Match any character NOT in brackets

### **Brace Expansion:**
- **`{a,b,c}`** - Brace expansion (multiple strings)

---

## 📞 SIGNALS

### **Common Signals:**
- **`SIGINT (2)`** - Interrupt signal (Ctrl+C)
- **`SIGTERM (15)`** - Termination signal
- **`SIGKILL (9)`** - Kill signal (cannot be ignored)
- **`SIGHUP (1)`** - Hangup signal (terminal disconnect)
- **`SIGQUIT (3)`** - Quit signal (Ctrl+\)

---

## 🎯 SHELL OPTIONS

### **Error Handling:**
- **`set -e`** - Exit on error
- **`set -u`** - Treat unset variables as error
- **`set -x`** - Debug mode (show commands)
- **`set -o pipefail`** - Pipe fails if any command fails

### **Extended Features:**
- **`shopt -s extglob`** - Enable extended globbing
- **`shopt -s nocasematch`** - Case insensitive matching

---

**📖 USAGE EXAMPLES:**

```bash
# Control Flow Example
if [ -f "$file" ]; then
    echo "File exists"
elif [ -d "$file" ]; then
    echo "Directory exists"
else
    echo "Not found"
fi

# String Operations Example
name="John"
echo "Hello, ${name^^}!"  # Uppercase: JOHN

# Array Example
files=($(ls *.txt))
echo "Found ${#files[@]} files"

# Arithmetic Example
result=$((10 + 5 * 2))
echo "Result: $result"

# Pattern Matching Example
for file in *.log; do
    echo "Processing: $file"
done
```

---

# CONCLUSION

This comprehensive Bash scripting guide covers everything from basic concepts to advanced cybersecurity applications. Bash scripting is an essential skill for system administrators, cybersecurity professionals, and anyone working with Linux/Unix systems.

## Key Takeaways:

1. **Start with Basics**: Master variables, loops, and conditional statements before advancing
2. **Practice Security**: Always validate inputs, use proper permissions, and follow security best practices
3. **Automate Responsibly**: Ensure scripts are reliable, error-handled, and well-documented
4. **Stay Legal**: Only use security tools and techniques on systems you own or have permission to test
5. **Keep Learning**: Bash scripting evolves, so stay updated with new features and security practices

## Next Steps:

- Practice with real-world scenarios
- Contribute to open-source projects
- Study shell scripting best practices
- Learn complementary skills like Python and PowerShell
- Stay updated with security trends and techniques

Remember: With great scripting power comes great responsibility. Use your knowledge ethically and legally.

---

**Happy Scripting! 🚀**
