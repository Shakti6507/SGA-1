# Q3 Explanation

- `rm -f original.txt hardlink.txt symlink.txt` cleaned any previous test files before starting the experiment.
- `echo "Linux link test file" > original.txt` created the original file for link analysis.
- `ln original.txt hardlink.txt` created a hard link sharing the same inode as the original.
- `ln -s original.txt symlink.txt` created a symbolic link that points to the original file path.
- `ls -li` showed inode numbers for the original file, hard link, and symbolic link.
- `stat original.txt hardlink.txt symlink.txt` provided metadata confirming that the hard link shared the same inode as the original while the symlink had its own inode.
- `cat original.txt`, `cat hardlink.txt`, and `cat symlink.txt` confirmed all three access methods returned the same content initially.
- `rm original.txt` deleted the original file without affecting the hard link data.
- `ls -li` again showed the hard link still existed with the same inode, while the symbolic link remained but no longer resolved.
- `cat hardlink.txt` still worked, but `cat symlink.txt` failed because the symlink target was removed.

The experiment demonstrates that hard links preserve file data after the original file is deleted, while symbolic links depend on the original path.