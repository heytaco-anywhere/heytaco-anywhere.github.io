---
title: 'Heytaco Settings'
date: 2019-02-11T19:27:37+10:00
draft: false
weight: 3
---

Heytaco supports Slack and Microsoft Teams. This section shows you how to set up Heytaco for both.

### Slack

Slack supports App to help people connect their tools and work more efficiently within Slack. Heytaco Anywhere is also a kind of Slack App.

##### Step 1: Create App

Firstly, we have to create [Slack App](https://api.slack.com/apps). Let's click the `Create App` button and fill out inputs.

![slack-create-app](/images/slack-create-app.png)

##### Step 2: Set up App

After creating App let's move to the `OAuth & Permissions` section. In this section, we need to set up the _redirect URLs_ and _scopes_. Firstly, let's add a new redirect URL with the `https://YOUR_HOST/slack/signin` format; secondly, add the `identity` and the `chat: write` into the user token scopes.

![slack-redirect-url](/images/slack-redirect-url.png)

![slack-scope](/images/slack-scope.png)

Then install the App into the workspace by clicking `Install to Workspace`.

##### Step 3: Configuration

### Microsoft Teams

TBD
