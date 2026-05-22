# Example: Stale Document Contamination

## Failure

An agent reads an old backend contract and treats it as current truth. The contract looks polished, so the agent uses it in a handoff. A future window then plans work against an API that no longer exists.

## Better Harness

Before writing a handoff or read-first index:

1. Compare old contracts with current code and runtime behavior.
2. Search for renamed or deleted routes.
3. Check package scripts, runbooks, and production behavior.
4. Classify stale material as historical, downgraded, rewritten, or delete candidate.

## Rule

Polish is not authority. Current code and runtime behavior outrank stale docs.
