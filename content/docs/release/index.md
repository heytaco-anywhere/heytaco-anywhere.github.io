---
title: 'Release Note'
date: 2019-02-11T19:27:37+10:00
weight: 6
---

Relase note of Heytaco Anywhere. You can check what is added, fixed and removed.

## Release Note

### v0.1.7

**Fixed**

* 🛠  Change the user is passed through OAuth twice for the `chat:write` scope.

### v0.1.6

**Fixed**

* 🛠  Fix type of `HEYTACO_ANYWHERE_HEYTACO_APP_SECRET` slice for enough tacos.

### v0.1.5

**Added**

* ✨  Block self-taco to prevent abusing.

**Fixed**

* 🐛  Change the length of access_token for Jira.

### v0.1.4

**Fixed**

* 🐛 Fix the `user_scope` of oAuth for slack; include `user.identity`.

### v0.1.3

**Fixed**

* 🐛 Import `mysql`, `postgres` packages.


### v0.1.2

**Fixed**

* 🛠 Change the limit of user count up to *10* for trial mode.
* 🛠 Refresh the token for expired Jira token.

### v0.1.1

**Fixed**

* 🐛 Fix the default value of `HEYTACO_ANYWHERE_STORE_SOURCE`(i.e. `/data/sqlite3.db`).

### v0.1.0

**Added**

* ✨ Initialize the project: Slack, Github, Jira supported.
