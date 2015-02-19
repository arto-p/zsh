# zsh
Some stuff for zsh

# Helpers for `run-help`

Here is some run-help helpers for certain commands, which allow use
some other commans/subcommands, e.g. git, xargs. Main idea is properly
process of main command's options:

```
  # sudo -u user vim<F1>
```

must call `man vim`, not `man sudo`.

 * run-help-docker
 * run-help-git
 * run-help-ip
 * run-help-sudo
 * run-help-xargs

# `ssh-agent`

Main problem with `ssh-agent` -- how to obtain right `SSH_AUTH_SOCK` if
you login from another terminal? This function simply check that
ssh-agent is up, properly working (has working socket) and then
write `SSH_AGENT_PID` and `SSH_AUTH_SOCK` to file and export.
After that your ssh can obtain keys from `ssh-agent`.
