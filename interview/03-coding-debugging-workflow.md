# Coding and Debugging Workflow

## Context

In interviews, the process matters as much as the final code. I need to communicate assumptions, handle edge cases, and test without going silent.

## Coding Problem Flow

1. Restate the problem.
2. Ask clarifying questions.
3. Write examples.
4. Discuss brute force.
5. Improve with data structures or patterns.
6. Code carefully.
7. Test normal, edge, and failure cases.
8. Analyze time and space complexity.

## Debugging Flow

```text
Reproduce -> Isolate -> Inspect data -> Test hypothesis -> Fix -> Regression check
```

## Useful Patterns

| Pattern | Use |
| --- | --- |
| Two pointers | Sorted arrays, pairs, windows |
| Sliding window | Contiguous subarray/string |
| Hash map | Frequency, lookup, dedup |
| Stack | Matching, monotonic problems |
| BFS | Shortest path in unweighted graph |
| DFS | Traversal, backtracking |

## Common Mistakes

- Coding before clarifying input constraints.
- Ignoring empty input.
- Not explaining trade-offs.
- Testing only the happy path.
- Panicking after a bug instead of tracing one example.

## Quick Reference

| Need | Say/do |
| --- | --- |
| Clarify | "Can values repeat?" |
| Edge case | Empty, one item, duplicates, large input |
| Complexity | State Big-O after solution |
| Debug | Walk through a failing example |
