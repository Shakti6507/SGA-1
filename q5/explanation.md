# Q5 Explanation

- `lsblk` listed available block devices and their mount points, identifying disks and loop devices.
- `mount | head -5` showed the top mounted filesystems, including overlay, proc, tmpfs, devpts, and sysfs.
- `df -h` reported disk usage statistics in a human-readable format, showing usable space and percentage usage.
- `df -i` reported inode utilization for mounted filesystems, showing inode availability and usage percentages.

Storage observations:
- `/dev/root` is 80% used and should be monitored to avoid running out of space.
- The overlay filesystem is at 33% usage, which is within safe limits.
- Inode usage is low across all filesystems, indicating no inode exhaustion.
- `/tmp` is very lightly used and not a concern.

Recommendations:
- Monitor `/dev/root` and remove unnecessary files or logs if it continues to grow.
- Review workspace data periodically to keep storage utilization under control.
