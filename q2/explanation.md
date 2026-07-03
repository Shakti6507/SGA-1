# Q2 Explanation

- `mkdir -p secure_workspace/{docs,src,logs}` created the project workspace directories in a secure structure.
- `touch secure_workspace/docs/plan.txt secure_workspace/src/app.txt secure_workspace/logs/activity.log` created the required files for documentation, source code, and logs.
- `ls -ld secure_workspace secure_workspace/*` displayed directory permissions before applying secure settings.
- `chmod 750 secure_workspace` and similar commands restricted directory access so only the owner has full access and the group can read/search.
- `chmod 640 secure_workspace/docs/plan.txt secure_workspace/src/app.txt secure_workspace/logs/activity.log` restricted file access so only the owner can write and group can read.
- `ls -ld secure_workspace secure_workspace/*` after modification confirmed the new permissions.
- `ls -l secure_workspace/*` confirmed file ownership and permissions inside each directory.
- `umask` showed the current default mask `0022`, explaining how default permissions are derived.

These steps protect project data by limiting write and read access to authorized users only.