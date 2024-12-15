# Lua Pairs Iterator Unexpected Behavior

This repository demonstrates a potential issue with Lua's `pairs` iterator when dealing with nested tables and modifications during iteration.  The `bug.lua` file contains code that showcases the unexpected behavior. The `bugSolution.lua` file offers a solution to mitigate this problem.

## Problem

Lua's `pairs` iterator iterates through the keys of a table. If you modify the table's structure (add, remove, or modify keys) during iteration, the iterator might skip entries or repeat them unexpectedly. This is because `pairs` relies on the internal structure of the table, which changes while the table is being modified. 

## Solution

The recommended approach to avoid issues is to iterate over a copy of the table or collect changes for later application, preventing modifications during iteration.