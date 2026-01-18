## ⚠️ Known Issue: Kernel Headers

This project currently depends on kernel headers that are known to be broken
for DKMS on ARM systems.

See upstream issue:
- cetola/mnt-build#5

Until this is resolved, DKMS module builds may fail with:
`Exec format error` due to x86_64 binaries in the headers package.
