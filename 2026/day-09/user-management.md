# Day 09 Challenge – Linux User & Group Management

## Users & Groups Created

### Users

* tokyo
* berlin
* professor
* nairobi

### Groups

* developers
* admins
* project-team

---

## Group Assignments

| User      | Groups                   |
| --------- | ------------------------ |
| tokyo     | developers, project-team |
| berlin    | developers, admins       |
| professor | admins                   |
| nairobi   | project-team             |

---

## Directories Created

### /opt/dev-project

* Group Owner: developers
* Permissions: 775

### /opt/team-workspace

* Group Owner: project-team
* Permissions: 775

---

## Commands Used

```bash id="3qjrqk"
useradd
passwd
groupadd
usermod
groups
mkdir
chgrp
chmod
touch
ls
```

---

## Verification

### Users Verified

```bash id="b1w04g"
cat /etc/passwd
```

### Groups Verified

```bash id="cfbx6y"
cat /etc/group
```

### Membership Verified

```bash id="8oicfo"
groups username
```

### Directory Permissions Verified

```bash id="rvupig"
ls -ld /opt/dev-project
ls -ld /opt/team-workspace
```

---

## What I Learned

1. Linux users and groups help manage access control.
2. Multiple users can collaborate through shared groups.
3. Directory permissions determine who can read, write, and execute files.
4. The `usermod -aG` command is used to add users to groups.
5. Proper permissions are important for secure system administration.

