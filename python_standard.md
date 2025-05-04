# Python Code Quality Guide: Writing Maintainable and Elegant Code

## Core Principles
- **Single Responsibility**: Each function, method or class should do exactly one thing well
- **Don't Repeat Yourself (DRY)**: Extract duplicated logic into helper functions
- **KISS (Keep It Simple, Stupid)**: Prefer straightforward solutions over clever tricks
- **Fail Fast**: Validate inputs early and make invalid states impossible

## Function Design
- **Small and focused**: Keep functions under 20-30 lines; each should fit on one screen
- **Clear intent**: Function name should clearly describe its purpose and effect
- **Pure when possible**: Prefer pure functions (same inputs → same outputs, no side effects)
- **Parameter limit**: Aim for 3 or fewer parameters; use dataclasses for related parameters
- **Return early**: Use guard clauses to handle edge cases at the beginning

## Code Organization
- **Progressive disclosure**: Public interfaces first, implementation details later
- **Context grouping**: Keep related functionality together
- **Hierarchical structure**: Layer code from high-level operations to low-level utilities
- **Logical separation**: Split files when they exceed 300-400 lines or mix concerns

## Naming and Documentation
- **Intention-revealing names**: Names should explain what, not how
- **Consistent terminology**: Use the same term for the same concept throughout
- **Meaningful docstrings**: Document 'why' more than 'what' (code already shows what)
- **Documentation to code ratio**: Less is more—good code mostly documents itself

## Error Handling
- **Specific exceptions**: Catch specific exceptions, not `Exception`
- **Contextual error messages**: Include relevant details in error messages
- **Error boundaries**: Handle errors at appropriate levels, don't pass exceptions across module boundaries
- **Fail gracefully**: Maintain system integrity when errors occur

## Pythonic Patterns
- **Use standard library tools**: Learn and use `collections`, `itertools`, `functools`, etc.
- **Leverage modern Python**: Use f-strings, walrus operator (:=), type hints where clarifying
- **Idiomatic constructs**: Use list/dict comprehensions, generators, context managers
- **Avoid premature optimization**: Write for clarity first, optimize only with evidence

## Testing and Maintainability
- **Testable by design**: Structure code to be easily tested without extensive mocking
- **Separation of concerns**: Distinguish between business logic, I/O, configuration
- **Immutability by default**: Prefer immutable data structures where possible
- **Explicit dependencies**: Make dependencies clear through parameters, not globals

## Code Review Checklist
- Would another developer immediately understand this code?
- Could I explain this function's purpose in one simple sentence?
- Have I eliminated all duplicated logic?
- Does each function do exactly one thing?
- Is there anything I could remove while preserving functionality?

---

**Remember**: Great code reads like well-written prose—it tells a clear story with minimal distractions. The best code is often the code you don't have to write.
