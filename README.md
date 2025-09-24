# Campus Course & Records Manager (CCRM)

## Project Overview

The Campus Course & Records Manager (CCRM) is a comprehensive console-based Java application designed to manage student records, courses, enrollments, and grades for educational institutions. This project demonstrates advanced Java SE features and follows modern software engineering practices.

## Features

- **Student Management**: Add, update, search, and manage student records
- **Course Management**: Create and manage course catalogs with instructor assignments
- **Enrollment System**: Handle student course enrollments with business rule validation
- **Grade Management**: Record marks, calculate GPAs, and generate transcripts
- **File Operations**: Import/export data in CSV format with NIO.2 APIs
- **Backup System**: Automated backup with recursive directory operations
- **Reports & Analytics**: Generate statistical reports using Stream API

## How to Run

### Prerequisites
- Java Development Kit (JDK) 8 or higher
- Any Java IDE (Eclipse, IntelliJ IDEA, VS Code) or command line

### Compilation and Execution

#### Using Command Line:
```bash
# Compile all Java files
javac -d . edu/ccrm/**/*.java

# Run the application
java edu.ccrm.CCRMApplication

# Run with assertions enabled (recommended)
java -ea edu.ccrm.CCRMApplication
```

#### Using Eclipse IDE:
1. Create a new Java Project
2. Copy all source files maintaining the package structure
3. Right-click on `CCRMApplication.java` → Run As → Java Application

## Evolution of Java

### Timeline of Major Java Releases:
- **1995**: Java 1.0 - Initial release with basic OOP features
- **1997**: Java 1.1 - Added inner classes, JavaBeans, JDBC
- **1998**: Java 1.2 (J2SE) - Collections Framework, Swing GUI
- **2000**: Java 1.3 - HotSpot JVM, JNDI
- **2002**: Java 1.4 - Assert, Regular Expressions, NIO
- **2004**: Java 5.0 - Generics, Annotations, Autoboxing, Enhanced for-loop
- **2006**: Java 6 - Scripting support, Web Services
- **2011**: Java 7 - Diamond operator, try-with-resources, NIO.2
- **2014**: Java 8 - Lambda expressions, Stream API, Date/Time API
- **2017**: Java 9 - Module system, JShell
- **2018**: Java 10 - Local variable type inference (var)
- **2018**: Java 11 - LTS version, HTTP Client API
- **2019**: Java 12/13 - Switch expressions, Text blocks (preview)
- **2020**: Java 14 - Pattern matching (preview), Records (preview)
- **2021**: Java 17 - LTS version, Sealed classes, Pattern matching

## Java Platform Comparison

| Feature | Java ME (Micro Edition) | Java SE (Standard Edition) | Java EE (Enterprise Edition) |
|---------|------------------------|----------------------------|------------------------------|
| **Target** | Mobile & embedded devices | Desktop & server applications | Enterprise web applications |
| **Status** | Largely deprecated | Current standard platform | Now Jakarta EE |
| **Libraries** | Minimal subset of SE | Complete standard library | SE + enterprise libraries |
| **Use Cases** | IoT devices, old mobile phones | Desktop apps, utilities | Web services, enterprise apps |
| **JVM** | Compact, optimized for limited resources | Full-featured HotSpot JVM | Full JVM + application servers |
| **Examples** | Nokia phones (legacy) | This CCRM application | Spring Boot, web applications |

## Java Architecture

### JDK (Java Development Kit)
- **Purpose**: Complete development environment for Java applications
- **Components**: 
  - Compiler (javac)
  - Debugger (jdb)
  - Documentation generator (javadoc)
  - Archive tool (jar)
  - JRE (includes JVM)
- **Usage**: Required for developing Java applications

### JRE (Java Runtime Environment)
- **Purpose**: Runtime environment for executing Java applications
- **Components**:
  - JVM (Java Virtual Machine)
  - Core libraries (java.lang, java.util, etc.)
  - Supporting files
- **Usage**: Required for running Java applications

### JVM (Java Virtual Machine)
- **Purpose**: Executes Java bytecode
- **Key Features**:
  - Platform independence ("Write Once, Run Anywhere")
  - Memory management and garbage collection
  - Just-In-Time (JIT) compilation
  - Security and sandboxing
- **Process**: Source code (.java) → Bytecode (.class) → Native machine code

### Interaction Flow:
```
Java Source Code (.java)
       ↓ (javac compiler in JDK)
Java Bytecode (.class)
       ↓ (JVM in JRE)
Native Machine Code
```

## Windows Installation Guide

### Step 1: Download JDK
1. Visit [Oracle JDK Downloads](https://www.oracle.com/java/technologies/javase-downloads.html)
2. Download the latest JDK for Windows (x64)
3. Run the installer (.exe file)

### Step 2: Installation Process
1. Double-click the downloaded installer
2. Follow the installation wizard
3. Choose installation directory (default: C:\Program Files\Java\jdk-{version})
4. Complete the installation

### Step 3: Set Environment Variables
1. Open System Properties (Windows + Pause → Advanced System Settings)
2. Click "Environment Variables"
3. Under System Variables, click "New":
   - Variable Name: `JAVA_HOME`
   - Variable Value: `C:\Program Files\Java\jdk-{version}`
4. Find "Path" in System Variables, click "Edit"
5. Add new entry: `%JAVA_HOME%\bin`
6. Click OK to save all changes

### Step 4: Verify Installation
Open Command Prompt and run:
```cmd
java -version
javac -version
```

**Expected Output:**
```
java version "17.0.2" 2022-01-18 LTS
Java(TM) SE Runtime Environment (build 17.0.2+8-LTS-86)
Java HotSpot(TM) 64-Bit Server VM (build 17.0.2+8-LTS-86, mixed mode, sharing)
```

## Eclipse IDE Setup

### Step 1: Download Eclipse IDE
1. Visit [Eclipse Downloads](https://www.eclipse.org/downloads/)
2. Download "Eclipse IDE for Java Developers"
3. Extract to desired location

### Step 2: Create New Project
1. Launch Eclipse
2. File → New → Java Project
3. Project Name: `CCRMApplication`
4. Use default location or specify custom path
5. JRE Version: Select installed JDK
6. Click "Finish"

### Step 3: Import Source Code
1. Right-click project → New → Package
2. Create packages: `edu.ccrm.domain`, `edu.ccrm.service`, etc.
3. Copy Java files to respective packages
4. Refresh project (F5)

### Step 4: Run Configuration
1. Right-click `CCRMApplication.java`
2. Run As → Java Application
3. To enable assertions:
   - Run → Run Configurations
   - Select your application
   - Arguments tab → VM arguments: `-ea`
   - Apply and Run

## Technical Requirements Mapping

| Requirement | Implementation | File/Class/Method |
|-------------|----------------|-------------------|
| **OOP Principles** | | |
| Encapsulation | Private fields with getters/setters | All domain classes |
| Inheritance | Person → Student, Instructor | Person.java, Student.java, Instructor.java |
| Abstraction | Abstract Person class with abstract methods | Person.java |
| Polymorphism | Person references to Student/Instructor objects | StudentService.java, CLI.java |
| **Design Patterns** | | |
| Singleton | AppConfig class | AppConfig.java |
| Builder | Course.Builder, Student.Builder | Course.java, Student.java |
| **Exception Handling** | | |
| Custom Exceptions | DuplicateEnrollmentException, MaxCreditLimitExceededException | domain package |
| Try-catch-finally | File operations, user input validation | FileIOService.java, CLI.java |
| Multi-catch | Exception handling in CLI | CLI.java |
| **File I/O (NIO.2)** | | |
| Path & Files APIs | File operations, backup system | FileIOService.java |
| Stream processing | CSV import/export | FileIOService.java |
| Directory operations | Backup creation, recursive file listing | FileIOService.java |
| **Collections & Streams** | | |
| Stream API | Filtering, mapping, collecting operations | All service classes |
| Lambda expressions | Predicates, comparators, functional interfaces | ComparatorUtil.java |
| Method references | Stream operations | CLI.java, service classes |
| **Date/Time API** | | |
| LocalDate | Registration dates, backup timestamps | Person.java, AppConfig.java |
| DateTimeFormatter | Backup folder naming | AppConfig.java |
| **Enums** | | |
| With constructors | Grade, Semester enums | Grade.java, Semester.java |
| Methods and fields | Grade point calculation | Grade.java |
| **Interfaces & Classes** | | |
| Interfaces | Persistable, Searchable | service package |
| Default methods | Diamond problem resolution | Persistable.java, Searchable.java |
| Abstract classes | Person class | Person.java |
| Nested classes | Static nested Name class, inner AcademicRecord | Person.java, Student.java |
| Anonymous classes | Custom comparator example | ComparatorUtil.java |
| **Control Structures** | | |
| Switch statements | Menu handling | CLI.java |
| Enhanced switch | Menu choice handling | CLI.java |
| Loops (all types) | while, do-while, for, enhanced-for | CLI.java |
| Break/continue | Loop control with labeled breaks | CLI.java |
| **Arrays & Utilities** | | |
| Arrays class | Sorting, searching operations | CLI.java |
| Array operations | Student/course array demonstrations | CLI.java |
| **Functional Programming** | | |
| Functional interfaces | Predicate, Function, Comparator | ComparatorUtil.java |
| Lambda expressions | Stream operations, event handling | Throughout project |
| **Assertions** | | |
| Invariant checking | Parameter validation, state verification | CCRMApplication.java |
| **Recursion** | | |
| Directory size calculation | Recursive file system traversal | FileIOService.java |
| File listing | Recursive directory listing with depth | FileIOService.java |

## Enabling Assertions

Assertions are disabled by default in Java. To enable them:

### Command Line:
```bash
java -ea edu.ccrm.CCRMApplication
# or
java -enableassertions edu.ccrm.CCRMApplication
```

### Eclipse IDE:
1. Run → Run Configurations
2. Select your application
3. Arguments tab → VM arguments: `-ea`
4. Apply and Run

### Sample Assertion Commands:
```bash
# Enable all assertions
java -ea MyClass

# Enable assertions for specific package
java -ea:edu.ccrm... MyClass

# Enable system assertions
java -esa MyClass
```

## Project Structure

```
edu/ccrm/
├── domain/                 # Domain model classes
│   ├── Person.java        # Abstract base class
│   ├── Student.java       # Student entity with Builder pattern
│   ├── Instructor.java    # Instructor entity
│   ├── Course.java        # Course entity with Builder pattern
│   ├── Enrollment.java    # Enrollment relationship
│   ├── Grade.java         # Grade enum with grade points
│   ├── Semester.java      # Semester enum
│   ├── DuplicateEnrollmentException.java
│   └── MaxCreditLimitExceededException.java
├── service/               # Business logic layer
│   ├── Persistable.java   # Generic persistence interface
│   ├── Searchable.java    # Search functionality interface
│   ├── StudentService.java # Student business operations
│   └── CourseService.java  # Course business operations
├── io/                    # File I/O operations
│   └── FileIOService.java # NIO.2 based file operations
├── util/                  # Utility classes
│   ├── ValidationUtil.java # Input validation utilities
│   └── ComparatorUtil.java # Lambda-based comparators
├── config/                # Configuration management
│   └── AppConfig.java     # Singleton configuration
├── cli/                   # Command line interface
│   └── CLI.java          # Main user interface
└── CCRMApplication.java   # Main application class
```

## Sample Data

The application includes sample data for testing:
- 3 pre-loaded students with different GPAs
- 3 pre-loaded courses from different departments
- Sample enrollments and grades

Additional test data can be imported from CSV files in the `test-data/` directory.

## Key Features Demonstrated

### Object-Oriented Programming
- **Encapsulation**: All domain classes use private fields with public accessors
- **Inheritance**: Person → Student/Instructor hierarchy with proper constructor chaining
- **Abstraction**: Person abstract class with abstract methods for role-specific behavior
- **Polymorphism**: Person references used to handle both Student and Instructor objects

### Design Patterns
- **Singleton**: AppConfig ensures single configuration instance
- **Builder**: Course and Student builders for complex object construction
- **Strategy**: Comparator utilities with different sorting strategies

### Functional Programming
- **Lambda Expressions**: Used extensively in Stream operations and event handling
- **Method References**: Constructor and method references in Stream processing
- **Functional Interfaces**: Custom predicates and functions for filtering and mapping

### Exception Handling
- **Custom Exceptions**: Business-specific exceptions for enrollment and credit limits
- **Multi-catch**: Handling multiple exception types in single catch block
- **Try-with-resources**: Automatic resource management for file operations

### File I/O with NIO.2
- **Path API**: Modern path handling for cross-platform compatibility
- **Files Utility**: Reading, writing, copying, and moving files
- **Stream Processing**: Reading CSV files line by line with streams
- **Recursive Operations**: Directory traversal and size calculation

## Error Handling & Validation

The application includes comprehensive error handling:
- Input validation for email formats, student IDs, course codes
- Business rule validation (credit limits, duplicate enrollments)
- File operation error handling with user-friendly messages
- Graceful handling of invalid user inputs

## Reports & Analytics

The system provides various reports using Stream API:
- Student statistics with GPA calculations
- Grade distribution analysis
- Department-wise course distribution
- Top students ranking
- Enrollment statistics

## Future Enhancements

Potential improvements for the system:
- Database integration using JDBC
- Web-based interface using Spring Boot
- REST API for external integration
- Advanced reporting with charts and graphs
- Email notification system
- Academic calendar integration

## Troubleshooting

### Common Issues:

1. **ClassNotFoundException**: Ensure all files are compiled and in the correct package structure
2. **File not found errors**: Check that data and backup directories exist
3. **Assertion errors**: Run with `-ea` flag to enable assertions
4. **Memory issues**: Increase heap size with `-Xmx512m` for large datasets

### Debug Commands:
```bash
# Verbose output
java -verbose:class edu.ccrm.CCRMApplication

# Debug mode
java -Xdebug -Xrunjdwp:transport=dt_socket,server=y,suspend=n,address=5005 edu.ccrm.CCRMApplication
```

## License

This project is developed for educational purposes as part of Java SE learning curriculum.

## Contact

For questions or issues related to this project, please refer to the course documentation or contact the development team.
