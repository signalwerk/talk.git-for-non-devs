---
theme: signalwerk
title: Git/GitLab/GitHub for Non-Developers
---

```fm
style: negative
background: true
```

## Hello _👋_

# {{process.content.frontmatter.title}}

_What do developers do?_

<footer>

2023 · Zurich · Stefan Huber

</footer>

--s--

## What is Git?

> Git is a _version control system_ that allows you to track _changes to your code over time_, collaborate with others on the same codebase, and revert to previous versions if necessary.

--s--

## Codebase

- We «checkin» the **codebase** using **Git**.
- A **repositories** is a **collection of files** that make up a project.
- GitLab is a **hosting service** for Git repositories.
- Think of it like a **Google Drive for code**

→ [Example](https://git.intern.migros.net/agentur-liip/job-ad-management/) (see commit-history)

<footer>

GitHub is a similar service like GitLab. GitHub is more popular with open source projects.

</footer>

--s--

## Branches

- we have different branches to **separate different features**
- we can **merge branches** together to combine features
- Think of it like an **elegant version of a copy** where you know what changed

Naming & merging according to [GIT-Workflow](https://wiki.liip.ch/display/TEAMBAZINGA/GIT-Workflow)

--s--

## Example · Base

### Existing codebase (`main`-branch)

```js
if (isMonday) {
  print(`I don't like Mondays`);
}
```

--s--

## Example · Requirements

### Ticket #MON-1

> As a user, I want to be able to see the current day of the week.

--s--

## Example · Implementation #MON-1

### Existing codebase (`main`-branch)

```js
if (isMonday) {
  print(`I don't like Mondays`);
}
```

### #MON-1 (`feature/MON-1-show-weekday` branch)

```js
print(`I don't like ${currentDay}`);
```

--s--

## Review

1. _Dev A_ **implements** on branch `feature/MON-1-show-weekday`
2. _Dev B_ is **reviewing** the code
3. _Dev A_ **fixes** the code
4. _Dev B_ **approves** the code
5. _Dev A_ **merges** the code into `main`

→ [Example](https://git.intern.migros.net/agentur-liip/job-ad-management/-/merge_requests) (see `Changes`-tab)

--s--

```fm
style: negative
background: true
```

# Merge conflicts _💥🧨_

--s--

## Problem

- Two developers are working **on the same file**
- Both developers make changes to _the same line_
- Git doesn't know **which change to keep**

--s--

## Example

### #MON-1 (`feature/MON-1-show-weekday` branch)

> As a user, I want to be able to see the current day of the week.

### #MON-2 (`feature/MON-2-be-positive` branch)

> As a user, I want to have a positive attitude.

--s--

## Example

### Existing codebase (`main`-branch)

```js
if (isMonday) {
  print(`I don't like Mondays`);
}
```

--s--

## Example

### Existing codebase (`main`-branch)

```js
if (isMonday) {
  print(`I don't like Mondays`);
}
```

### #MON-1 (`feature/MON-1-show-weekday` branch)

```js
print(`I don't like ${currentDay}`);
```

--s--

## Example

### Existing codebase (`main`-branch)

```js
if (isMonday) {
  print(`I don't like Mondays`);
}
```

### #MON-2 (`feature/MON-2-be-positive` branch)

```js
if (isMonday) {
  print(`I like Mondays`);
}
```

--s--

## Example

### #MON-1 & #MON-2 diff

```diff
-- if (isMonday) {
--   print(`I don't like Mondays`);
++   print(`I like Mondays`);
++ print(`I don't like ${currentDay}`);
-- }
```

--s--

## Example

### #MON-1 & #MON-2 merged (by hand)

```js
print(`I like ${currentDay}`);
```

--s--

## What are pipelines?

- Pipelines are a **series of steps** that run **automatically** when we push code
- Pipelines are **defined per project**
- Typically, pipelines **run tests** and **deploy** the code

→ [Example](https://git.intern.migros.net/agentur-liip/job-ad-management/-/pipelines)

--s--

## Recap

- **Repository:** A repository is a central location where all the versions of a project are stored.
- **Commit:** A commit is a snapshot of the changes made to a repository.
- **Branch:** A branch is a copy of the repository that allows for independent development.

--s--

## Recap

- **Merge:** Merging is the process of combining two or more branches into a single branch.
- **Pull/Merge request:** A pull request is a way of proposing changes to a repository.
- **Pipeline:** A pipeline is a series of steps that run automatically when we push code.

--s--

```fm
style: negative
background: true
```

## exit 0; thx

# Questions?

--s--

## Tags

- Tags are used to mark _a specific point in the repository’s history_.
- Tags are usually used to **mark a release**.

