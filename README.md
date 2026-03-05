# git-hooks

A set of Git hook scripts that I have honed over the years.

Use `./install-git-hooks` to install them in every repository contained in
the directories of your `CDPATH`.

Don't have a `CDPATH` set? It's just like the PATH variable, but for the cd
command. 

Example (put this in your startup file, e.g. `~/.bashrc` or `~/.zshrc`):

```bash
export CDPATH=~:~/src:~/work
```

## pre-commit

My pre-commit hook prevents from making some of my most common mistakes:

- accidentally committing into the main branch
- accidentally committing some temporary changes I had added while debugging
  something and forgot to undo.

  Now I just add a comment containing the word `nocommit`, and pre-commit will
  catch it.
- accidentally committing secret values in config files.

  This doesn't happen
  "often", but I added it ages ago when I was responsible for onboarding a
  service that had lots of secrets in its config files.

## pre-push:

So far the only things I've implemented in pre-push are for Rust projects:

- ensure that I've updated the Cargo.toml version.
- ensure that I've run cargo fmt.
