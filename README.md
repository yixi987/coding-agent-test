# coding-agent-test

A minimal Java project used for testing coding-agent workflows.

## Overview

The project contains a single class, `Main`, with a **binary search** implementation and a command-line driver. It is intentionally kept simple so that automated agents can explore, analyse, and fix the code.

## Project Structure

```
src/
  Main.java   – Binary search implementation and CLI entry point
test.iml      – IntelliJ IDEA module descriptor
```

## How It Works

`Main.binarySearch(int[] arr, int target)` searches a **sorted** integer array for `target` and returns its index, or `-1` if not found.

The `main` method accepts command-line arguments where all but the last value form the array and the last value is the search target.

```
java Main <array elements…> <target>
# Example – search for 5 in [1, 2, 3, 4, 5]:
java Main 1 2 3 4 5 5
# Output: Result index: 4
```

## Known Bug

The while-loop condition in `binarySearch` uses `i < j` instead of `i <= j`, which causes the method to miss elements when the search narrows down to a single remaining candidate. The correct condition is:

```java
while (i <= j) { ... }
```

## Requirements

- Java 8 or later
- IntelliJ IDEA (optional, for IDE support via `test.iml`)
