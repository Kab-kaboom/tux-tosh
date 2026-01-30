# Linux User and Permission Management Task

## Part 1: User Creation
I created three users: **Tupu** (via adduser), **Lupu** (via useradd), and **Hupu** (a system user).

![User List Screenshot](linux assignment 3(1).png)

## Part 2: Sudo Privileges
Tupu and Lupu were added to the sudo group to allow administrative access.

## Part 3: Task 5 - Shared Project Directory
To allow Tupu and Lupu to collaborate in `/opt/projekti`, I implemented a shared group and the **SetGID** bit.

### Steps Taken:
1. **Group Creation:** Created a group named `projekti`.
2. **User Assignment:** Added Tupu and Lupu to the group.
3. **Set Ownership:** Changed the directory group to `projekti`.
4. **Special Permissions:** Applied `sudo chmod 2770 /opt/projekti`.

### Why this works:
The `2` in `2770` is the **SetGID bit**. As shown in the screenshot below, when Tupu creates a file, it is automatically owned by the `projekti` group. This allows Lupu (who is in the same group) to edit it immediately.

![Permissions Screenshot](linux assignment 3(2).png)

### Verification:
* The directory shows `drwxrws---` (the 's' confirms SetGID).
* The test file shows group `projekti` despite being created by user `tupu`.
