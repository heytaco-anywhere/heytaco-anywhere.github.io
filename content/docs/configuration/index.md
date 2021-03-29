---
title: 'Configuration'
date: 2019-02-11T19:27:37+10:00
weight: 3
---

Heytaco Anywhere is connected by OAuth. It is necessary to configure Slack or Microsoft Teams. It depends on your Heytaco platform. And you should select one of the services to communicate with Heytaco and configure the OAuth setting for App. 

### Contents

* [Slack](#slack)
* [Microsoft Teams](#microsoft-teams)
* [Github](#github)


### Slack

Slack supports App to help people connect their tools and work more efficiently within Slack. Heytaco Anywhere is also a kind of Slack App.

##### Step 1: Create App

Firstly, we have to create [Slack App](https://api.slack.com/apps). Let's click the `Create App` button and fill out inputs.

![slack-create-app](/images/slack-create-app.png)

##### Step 2: Set up App

After creating App let's move to the `OAuth & Permissions` section. In this section, we need to set up the _redirect URLs_ and _scopes_. Firstly, let's add a new redirect URL with the `https://YOUR_HOST/slack/signin` format; secondly, add the `identity` and the `chat: write` into the user token scopes.

![slack-redirect-url](/images/slack-redirect-url.png)

![slack-scope](/images/slack-scope.png)

Then install the App into the workspace by clicking `Install to Workspace`. ([Slack Doc](https://api.slack.com/authentication/basics#start))

### Microsoft Teams

TBD 

### Github 

Github provides OAuth App. It makes Heytaco Anywhere reads Github login.

#### Step 1: Create App

In the organization, move to **"Settings > Developer Settings > OAuth settings"** to configure OAuth. 

After click New OAuth App, you can see the page. You should fill out the Homepage URL as the `https://YOUR_HOST` format and the Authorization callback URL as the `https://YOUR_HOST/service/signin` format. ([Github Doc](https://docs.github.com/en/developers/apps/creating-an-oauth-app))

![github-create-app](/images/github-create-app.png)

