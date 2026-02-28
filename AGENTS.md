```markdown
# AGENTS.md - Guidelines for AI Coding Agents

These guidelines are designed to ensure the creation and maintenance of high-quality AI coding agents within this repository. Adherence to these principles will promote maintainability, reliability, and scalability.

## 1. DRY (Don't Repeat Yourself)

*   All code should have a single, well-defined purpose.
*   Modules and functions should perform distinct tasks.
*   Refactoring should target eliminate redundant code, not simply rearrange existing code.
*   Consider creating reusable components and abstractions to simplify code.

## 2. KISS (Keep It Simple, Stupid)

*   Prioritize clarity and readability over complex solutions.
*   Strive for concise code that is easy to understand.
*   Avoid unnecessary abstraction or layers of indirection.
*   Keep functions and modules small and focused.

## 3. SOLID Principles

*   **Single Responsibility Principle:** Each class or module should have one well-defined responsibility.
*   **Open/Closed Principle:** Classes and modules should be open for extension but closed for modification.
*   **Liskov Substitution Principle:**  Subclasses should be substitutable for their base classes without altering the correctness of the program.
*   **Interface Segregation Principle:** Clients shouldn’t be forced to depend on methods they don’t use.
*   **Dependency Inversion Principle:** High-level modules should be dependent on interfaces, not implementations.

## 4. YAGNI (You Aren’t Gonna Need It)

*   Avoid premature implementation of features.
*   Implement only what is absolutely required to accomplish a specific task at a given point in time.
*   Refactor only when a new feature or requirement emerges.
*   Focus on functionality, not unnecessary complexity.

## 5. Code Length & Structure

*   Maximum code length: 180 lines.
*   Code should be easily parsed and understood.
*   Use consistent naming conventions.
*   Employ comments to explain complex logic or non-obvious decisions.
*   Properly document functions and modules with docstrings.

## 6. Test Coverage

*   All development must be productive.
*   Focus on automated unit tests.
*   Aim for at least 80% test coverage for all major code components.
*   Test cases should cover edge cases and boundary conditions.
*   Test suites should be organized logically.

## 7. File Structure

*   Files should adhere to a consistent directory structure.
*   Each file should represent a logical unit of functionality.
*   Document file contents with a concise summary.
*   Use descriptive filenames.

## 8.  AGENTS.md File Content Guidelines

*   The file must be cleanly formatted using a standard markdown syntax.
*   Use appropriate line breaks to improve readability.
*   Ensure appropriate indentation.
*   Prioritize clarity over excessive formatting.

## 9.  API Documentation (if applicable)

*   For any functions or classes that expose an API, provide clear and concise documentation.
*   Documentation should follow established standards (e.g., OpenAPI/Swagger).
*   Include examples of usage.

## 10.  Version Control

*   All code should be committed to a version control system (e.g., Git).
*   Use appropriate branching strategies.
*   Implement pull request workflows for code reviews.

## 11.  Testing Framework Considerations

*   Utilize a chosen testing framework for automated testing.
*   Test frameworks should be readily available and well-documented.

## 12.  Documentation Requirements

*   Include a README file describing the project's purpose, setup, and usage.
*   Document the purpose of each module, function, and class.
*   Explain assumptions and dependencies.

## 13.  Error Handling

*   Implement robust error handling to prevent unexpected behavior.
*   Log errors effectively for debugging and monitoring.

## 14.  Concurrency Considerations (If Applicable)

*   If concurrency is involved, design the agent to avoid race conditions and deadlocks.
*   Utilize appropriate synchronization primitives.

## 15.  Data Structures & Algorithms

*   Choose data structures and algorithms that are appropriate for the task.
*   Ensure efficiency in data processing.

These guidelines are meant to serve as a foundational framework for the AGENTS.md project. Continuous review and adaptation are encouraged to maintain the repository's quality and maintainability.
```