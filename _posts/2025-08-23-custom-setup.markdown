The following custom alias helps me with using a fuzzy finder `fzf` for switching branches. No more pain of remembering or copy pasting branch names!
```bash
alias branch='
  git branch -a | grep -v "^\*" |
  fzf --height=20% --reverse --info=inline |
  sed "s#remotes/[^/]*/##" |
  xargs -I{} git switch {}
'
```
