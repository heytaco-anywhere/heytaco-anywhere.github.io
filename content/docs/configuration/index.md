---
title: 'Configuration'
date: 2019-02-11T19:27:37+10:00
weight: 4
---

Heytaco Anywhere is connected by OAuth. It is necessary to configure Slack or Microsoft Teams. And also you need to configure a service to communicate with HeyTaco!.

## Contents

* [Slack](#slack)
* [Microsoft Teams](#microsoft-teams)
* [Github](#github)
* [Jira](#jira)


## Slack

Slack supports App people connect their tools and work more efficiently within Slack. Heytaco Anywhere is also a kind of Slack App.

### Step 0: Create a new channel

To send the 🌮 message, it needs a new slack channel. Let's add a new channle, such as "taco", and get the channel id in the browser. Check [here](https://stackoverflow.com/questions/40940327/what-is-the-simplest-way-to-find-a-slack-team-id-and-a-channel-id).

figure) Get channel id

![slack-channel-id](/images/slack-channel-id.png)

### Step 1: Create App

Firstly, we have to create [Slack App](https://api.slack.com/apps). Let's click the **Create App** button and fill out inputs.

![slack-create-app](/images/slack-create-app.png)

### Step 2: Set up App

After creating App let's move to the **OAuth & Permissions** section. In this section, we need to set up the *redirect URLs* and *scopes*. Firstly, let's add a new redirect URL with the `https://YOUR_HOST/slack/signin` (or `http://YOUR_HOST/slack/signin`) format; secondly, add the `identity.basic` scope and the `chat:write` scope into the user token scopes.

figure) Slack Redirect URLS

![slack-redirect-url](/images/slack-redirect-url.png)

figure) Slack Scope

![slack-scope](/images/slack-scope.png)

## Microsoft Teams

**WIP**

## Github 

### Step 1: Create App

In the organization, move to **Settings > Developer Settings > OAuth settings** to configure OAuth. 

After click New OAuth App, you have to fill out the Homepage URL as the `https://YOUR_HOST` format and the Authorization callback URL as the `https://YOUR_HOST/github/signin` format. ([Github Doc](https://docs.github.com/en/developers/apps/creating-an-oauth-app))

figure) Create Github OAuth App

![github-create-app](/images/github-create-app.png)

### Step 2: Create Webhook 

In the organization, move to **Settings > Webhooks** to configure the webhook.

After click Add webhook, you have to fill out the Payload URL and the Content-Type are required; The Payload URL format has to be `https://YOUR_HOST/github/hooks`, and the Content-Type has to be `application/json` format; (We recommend you should set the signing secret for security.)

And we have to select events the server listens to the event, click these events enabled: `Issue comments`, `Pull request reviews`, and `Pull request review comments`.

figure) Create Github Webhook

![github-create-webhook](/images/github-create-webhook.png)


## Jira

### Step 1: Create App

To connect with Jira, you have to create App in Atlassian Developer and make it public. Let's move to the [Atlassian Developer Console](https://developer.atlassian.com/console/myapps/) and create a new App. For OAuth, you have to configure the Callback URL and Permissions; The Callback URL has to be `https://YOUR_HOST/jira/signin` and it can be configured in the *Authorization* section; Permissions requires `View user profiles` and `View Jira Issue data` of Jira, it can be configured in the *Permissions* section. ([JIRA oAuth](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/))

To make your teammates access the App for authentication you have to make the App public. 

figure) App Authorization

![atlassian-app-authorization](/images/atlassian-app-authorization.png)

figure) App Permissions

![atlassian-app-permissions](/images/atlassian-app-permissions.png)

figure) App Distribution

![atlassian-app-distribution](/images/atlassian-app-distribution.png)

### Step 2: Create Webhook

In your JIRA workspace, move to **Settings > System > WebHooks**.

After click Create a Webhook button, you have to fill out the URL with `https://YOUR_HOST/jira/hooks`, and click the Comment `created` event enabled.

![atlassian-app-webhook](/images/atlassian-app-webhook.png)

