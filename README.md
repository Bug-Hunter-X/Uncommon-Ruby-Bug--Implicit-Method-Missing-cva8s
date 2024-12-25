# Uncommon Ruby Bug: Implicit Method Missing

This repository demonstrates a subtle bug in Ruby related to how instance variables are handled, particularly when using methods with the same name as the instance variable.  The issue arises when attempting to modify the instance variable indirectly, triggering an implicit method missing error instead of correctly modifying the variable.

## The Problem

In Ruby, if you try to assign a value to something that looks like an instance variable (like `my_object.value = 20`) but there's no corresponding writer method (`value=`), Ruby will try to invoke a method named `value=` and fail if it doesn't exist.

## The Solution

This can be solved in several ways:
1. **Explicit writer method:** Define a `value=` method to handle assignments.
2. **Direct access:** Use `@value` directly to set the instance variable.  Although direct instance variable access is generally discouraged, it solves the immediate issue.

## How to Reproduce

1. Clone this repository.
2. Run the `bug.rb` file.  You will see an error.
3. Examine the `bugSolution.rb` file to see a corrected version of the code.
