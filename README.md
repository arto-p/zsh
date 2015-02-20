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

# `seconds2time`

Convert seconds to time according to format:

```for i in {10..19}; do seconds2time "$[2**$i]: %d %H:%M:%S" $[2**$i]; done  2:04 (0)
1024: 0 00:17:04
2048: 0 00:34:08
4096: 0 01:08:16
8192: 0 02:16:32
16384: 0 04:33:04
32768: 0 09:06:08
65536: 0 18:12:16
131072: 1 12:24:32
262144: 3 00:49:04
524288: 6 01:38:08
```
