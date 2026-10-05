# Notes

## Summary of changes

I focused on correctness, reliability, and pagination/search behavior across the application.

On the frontend, I fixed stale API responses, loading/error handling, pagination reset when filters change, and added search debouncing.

On the backend, I corrected the search/filter SQL grouping, removed the artificial request delay, added validation for pagination and status parameters, moved pagination to the database, and handled `%` and `_` as literal search characters.

I also updated the Oracle reference queries to keep their filtering and pagination behavior consistent with the application.

## What I chose not to change

I avoided large architectural changes, UI redesigns, and unrelated refactoring because this was intended to be a focused patch exercise.

I also did not make changes to the existing API shape or project structure.

## Biggest remaining risk

The Oracle PL/SQL artifact was reviewed and updated, but I could not runtime-test it because I did not have an Oracle database available locally. This would be the first area I would verify with more time.

## Tools / AI used  

I used Codex/ChatGPT to help inspect the codebase, reason about potential edge cases, and review proposed fixes. I manually ran the application, reproduced important behaviors, reviewed the changes, and verified the frontend build, backend compilation, and H2 behavior locally.