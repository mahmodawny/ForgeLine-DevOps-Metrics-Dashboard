# Debugging and Linting Summary

## 1. Why This Matters

Software development requires more than writing code. Developers must verify that their code works correctly, identify errors, and maintain consistent coding standards.

Debugging and linting help developers detect problems early, improve code quality, and reduce issues before submitting changes for review.

## 2. Core Concepts

### Debugging

Debugging is the process of identifying, analyzing, and fixing errors in a software application.

A debugger allows developers to pause program execution and inspect the program state to understand why an error occurs.

### Breakpoint

A breakpoint is a marker placed on a specific line of code. When program execution reaches that line, the debugger pauses execution.

Breakpoints allow developers to inspect variables and understand how the program behaves at a particular point.

### Call Stack

The call stack shows the sequence of function calls that led to the current execution point.

It helps developers understand how the program reached a particular line of code and identify where an error originated.

### Stack Trace

A stack trace is a report showing the sequence of function calls that occurred before an error or exception.

It helps developers locate the source of an error and understand the execution path.

### Local Variables

Local variables are variables available within the current function or execution scope.

Developers can inspect their values while the debugger is paused to identify unexpected data.

### Linter

A linter is a static code analysis tool that examines source code without executing it.

It identifies potential errors, coding-style violations, and suspicious code patterns.

## 3. Using Debuggers in an IDE

Developers can use the debugging tools integrated into an IDE to investigate application errors.

### Basic Debugging Workflow

1. Open the project in the IDE.
2. Identify the section of code that may contain an error.
3. Set a breakpoint on the relevant line.
4. Start the application using the debugger.
5. Wait until execution reaches the breakpoint.
6. Inspect local variables and their current values.
7. Examine the call stack to understand the sequence of function calls.
8. Use debugging controls to continue execution step by step.
9. Identify the root cause and fix the error.
10. Run the application again to verify the correction.

### Common Debugging Controls

- **Continue:** Resume program execution until the next breakpoint.
- **Step Over:** Execute the current line without entering called functions.
- **Step Into:** Enter a function to inspect its internal execution.
- **Step Out:** Finish executing the current function and return to its caller.

## 4. Inspecting Call Stacks and Stack Traces

When execution pauses at a breakpoint, developers should inspect the call stack to understand how the current function was reached.

The call stack provides information about active function calls and their execution order.

When an exception occurs, the stack trace provides details about the error and the sequence of calls that led to it.

### Recommended Investigation Steps

1. Locate the error message or exception.
2. Read the stack trace to identify the affected file and line.
3. Examine the function calls leading to the error.
4. Set a breakpoint near the suspected source.
5. Inspect local variables and their values.
6. Trace the execution flow to identify the root cause.
7. Apply the required correction and test again.

## 5. Local Linting and Code Quality

Linting is an important part of the pre-submission verification process.

Developers should run the configured linter locally before pushing changes or submitting a Pull Request.

### Local Linting Command

```bash
npm run lint:check
```

This command runs the linting script configured in the project's package.json file.

### Pre-Submission Verification

Before submitting changes, developers should:

1. Run the local linting command.
2. Review all reported errors and warnings.
3. Fix coding-style violations and potential issues.
4. Review the modified files.
5. Check the Git diff for unintended changes.
6. Confirm that the working tree contains only intended modifications.
7. Submit the Pull Request after completing verification.

## 6. Debugging and Linting: Key Differences

| Aspect | Debugging | Linting |
|---|---|---|
| Purpose | Find and fix runtime or logical errors | Detect code-quality issues |
| Execution | Examines program execution | Analyzes source code statically |
| Tools | IDE Debugger | Linter |
| Main Features | Breakpoints, variables, call stack | Rules, warnings, errors |
| Timing | During investigation and testing | Before code submission and review |

## 7. Conclusion

Debugging and linting are essential practices in maintaining software quality.

Debuggers help developers investigate execution behavior, inspect variables, and identify the root cause of errors.

Linters detect potential code-quality problems before changes are submitted.

Combining both practices with Git review workflows helps ensure that changes are reliable, maintainable, and ready for peer review.