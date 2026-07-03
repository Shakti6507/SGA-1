# Q1 Explanation

- `whoami` was executed to identify the current user account, which returned `codespace`.
- `groups` showed the groups associated with the user, indicating access to various development tools.
- `echo "$SHELL"` printed the active shell, confirming the environment uses `/bin/bash`.
- `pwd` displayed the current working directory as `/workspaces/SGA-1/q1`.
- `ls -ls` listed directory contents and confirmed the workspace currently has no visible files.
- `curl -s --max-time 10 https://youtube.com > /dev/null && echo "Network: youtube.com reachable"` verified network connectivity to an external site.
- `umask` revealed the default file creation mask of `0022`, which restricts group and others from write permissions by default.

These commands confirm the environment is set up correctly, the user identity and shell are known, and network access is available.