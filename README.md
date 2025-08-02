# Code Debugging Agent with LangGraph

This project implements an AI-powered code debugging assistant using the LangGraph framework. The agent is designed to analyze code, identify bugs, suggest solutions, and provide detailed explanations to streamline the debugging process for developers.

### **Features**

* **Bug Identification**: Automatically detects syntax errors, runtime issues, and potential logical bugs.

* **In-depth Analysis**: Utilizes tools to assess code complexity and inspect the Abstract Syntax Tree (AST) for static issues.

* **Stateful Workflow**: Employs a state machine to move through a logical sequence of debugging operations.

* **Graceful Error Handling**: Manages internal errors to provide partial analysis and helpful tips even when a full solution can't be generated.

### **How It Works**

The agent is built as a `StateGraph` where each node represents a step in the debugging process:

1. **`identify_bugs`**: The entry point, which performs an initial analysis.

2. **`analyze_code`**: Conducts a deeper inspection of the code's structure and complexity.

3. **`generate_fixes`**: Proposes solutions to the identified problems.

4. **`create_explanation`**: Summarizes the findings in a comprehensive report.

5. **`handle_error`**: A terminal node for managing any failures in the workflow.

The agent's flow is controlled by a `DebuggingStatus` enum, which directs the graph from one node to the next based on the outcome of the current step.

### **Getting Started**

To run the agent, you need to define your code snippet and any known error messages. The main function will then process the input and print the results.

**Usage Example:**

```python
# 1. Define the code to be debugged
test_code = """
def calculate_average(numbers):
    total = 0
    for num in numbers
        total += num
    return total / len(numbers)
"""

# 2. Provide any known error message
error_message = "SyntaxError: invalid syntax"

# 3. Run the debugging assistant
# (Assuming the run_debugging_assistant function is defined)
run_debugging_assistant(test_code, error_message)
