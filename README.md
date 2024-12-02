# Samba Disk Space Free for Subdirectories

## Issue:
The Samba daemon does not report all available disk space when the path contains multiple disks.

## Solution:
This script calculates and outputs the correct total and free space for a given directory, including subdirectories on different mount points. By default, it checks the top-level directories, but it can be modified to include subdirectories by setting the `recursive` variable to `true`.

## Setup Instructions:

1. **Copy the script to a directory**

    ```bash
    sudo cp samba-dfree-subdir /usr/local/bin/samba-dfree-subdir
    ```

2. **Make the script executable**

    ```bash
    sudo chmod +x /usr/local/bin/samba-dfree-subdir
    ```

3. **Configure Samba**

    Edit your `smb.conf` and add the following line:

    ```bash
    dfree command = /usr/local/bin/samba-dfree-subdir
    ```
