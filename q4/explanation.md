# Q4 Explanation

- `rm -f app.log stdout.txt stderr.txt combined.txt` removed old files so the investigation begins clean.
- `echo "sample log line" > app.log` created a log file to inspect file access behavior.
- `lsof | head -n 20` displayed currently open files on the system.
- `exec 3<app.log` opened `app.log` on file descriptor 3 for reading.
- `lsof -p $$ | grep app.log` confirmed the current shell process had file descriptor 3 open for `app.log`.
- `ls -l /proc/$$/fd | grep app.log` verified the file descriptor mapping in `/proc`.
- `ls -l /proc/$$/fd` listed active file descriptors for the running shell.
- `ls -l > stdout.txt` redirected standard output to a file.
- `ls /not_a_real_path 2> stderr.txt` redirected standard error from a failing command.
- `(ls -l && ls /not_a_real_path) > combined.txt 2>&1` combined both stdout and stderr into one file.
- `ulimit -a` displayed shell resource limits, including file descriptors and memory.
- `exec 3<&-` closed the extra file descriptor opened for the log file.

These commands showed how Linux manages file descriptors, output redirection, and resource limits for process I/O.