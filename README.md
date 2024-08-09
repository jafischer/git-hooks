# git-hooks

## pre-commit
My pre-commit hook covers my ass from making some of my most common mistakes:
- accidentally committing into the main branch
- accidentally committing some temporary changes I had added while debugging 
  something and forgot to undo.

  Now I can just add a `don't commit` comment, and pre-commit will catch it.
- accidentally committing secret values in config files.

  This doesn't happen
  "often", but I added it ages ago when I was responsible for onboarding a 
  service that had lots of secrets in its config files.

## pre-push:
So far the only thing I've implemented in pre-push is for Rust projects:
- ensure that I've updated the Cargo.toml version whenever pushing a branch.
