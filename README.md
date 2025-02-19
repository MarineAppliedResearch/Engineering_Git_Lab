# Git Collaboration Lab

## Overview

This lab introduces the basics of Git for collaborative engineering projects. Participants will learn how to clone a repository, create and switch branches, make changes, and resolve merge conflicts.

---

## Step 1: Setting Up the Repository

Before creating and switching branches, ensure that the repository is correctly set up.

1. **Clone the repository (if you haven't already):**

   ```sh
   git clone https://github.com/MarineAppliedResearch/Engineering_Git_Lab
   cd Engineering_Git_Lab
   ```

2. **Ensure your repository is up to date:**

   ```sh
   git pull origin master
   ```

3. **Check your current branch:**

   ```sh
   git branch
   ```

   You should see `master` as the current branch.

---

## Step 2: Creating and Switching Branches

Each participant will create their own branch to work independently.

1. **Create and switch to your assigned feature branch:**

   - **Isaac (working on sensors):**
     ```sh
     git checkout -b feature-update-sensors
     ```
   - **Neal (working on data processing):**
     ```sh
     git checkout -b feature-update-processing
     ```
   - **Kyle (working on dashboard updates):**
     ```sh
     git checkout -b feature-update-dashboard
     ```

2. **Verify that you have switched branches:**
   ```sh
   git branch
   ```
   The active branch will be marked with an asterisk (`*`), confirming that you are working in the correct branch.

---

## Step 3: Editing the Project Specification

Each participant will modify a different section of `project_spec.txt`.

- **Isaac**: Modify the sensor support section.
  ```
  The system will support temperature, pressure, and humidity sensors.
  ```
- **Neal**: Modify the data processing section.
  ```
  The system will use AI-powered real-time data processing algorithms.
  ```
- **Kyle**: Modify the dashboard description.
  ```
  The user interface will provide a dashboard with real-time graphs and historical trend analysis.
  ```

After making changes, each participant should commit and push their updates:
```sh
   git add project_spec.txt
   git commit -m "Updated project specifications"
   git push origin <your-branch>
```

---

## Step 4: Merging and Resolving Conflicts

1. **Isaac merges first (no conflict expected):**
   ```sh
   git checkout master
   git pull origin master
   git merge feature-update-sensors
   git push origin master
   ```

2. **Neal merges next (conflict expected with Isaac's change):**
   ```sh
   git checkout master
   git pull origin master
   git merge feature-update-processing
   ```
   - If a merge conflict occurs, Git will indicate a conflict in `project_spec.txt`.
   - Open the file and resolve the conflict by keeping both changes.
   - Save the file, then run:
     ```sh
     git add project_spec.txt
     git commit -m "Resolved conflict by merging sensor and processing updates"
     git push origin master
     ```

3. **Kyle merges last (no conflict expected):**
   ```sh
   git checkout master
   git pull origin master
   git merge feature-update-dashboard
   git push origin master
   ```

---

## Step 5: Verifying the Final Version

After all changes have been merged, everyone should update their local copy:

```sh
   git checkout master
   git pull origin master
```

The final version should include all modifications from Isaac, Neal, and Kyle.

---

