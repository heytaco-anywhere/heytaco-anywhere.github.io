---
title: 'Get started'
date: 2019-02-11T19:27:37+10:00
weight: 2
---

Let's install Heytaco Anywhere. In this example, we're going to connect Heytaco(Slack) with Github.

### Step 1: Create HeyTaco! App

To send  🌮  in other services, we need to create a new HeyTaco! application that interacts with HeyTaco!.  At [here](https://www.heytaco.chat/team/apps/create), you can create a new App with the name Heytaco Anywhere like the following:

Download the [Heytaco Anywhere Icon](/images/taco.png).

figure) Create HeyTaco! App

![Heytaco Create App](/images/heytaco-create-app.png)

figure) List HeyTaco! App

![Heytaco Apps](/images/heytaco-apps.png)


### Step 2: Configuring Slack 

To make Heytaco Anywhere acts on behalf of a Slack user, we have to use Slack OAuth. Here is the [guide](/docs/configuration#slack) to configure Slack.

### Step 3:  Configuring Github

To map Github users and listen to the issue comment (or review comment), we need Github OAuth and Webhook. Here is the [guide](/docs/configuration#github) to configure Github.

### Step 4: Download

The Heytaco Anywhere server is distributed as a lightweight Docker image. The image is self-contained and does not have any external dependencies.

```shell
$ docker pull heytacoanywhere/heytaco-anywhere:0.1
```

### Step 5: Configuration

The Heytaco Anywhere server is configured using environment variables. This article references a subset of configuration options, defined below. See [Configuration](/docs/reference) for a complete list of configuration options.

**HEYTACO_ANYWHERE_SERVER_HOST**: Required string value provides your external hostname.

**HEYTACO_ANYWHERE_SERVER_PROTO**: Required string value provides your external protocol scheme. This value should be set to `http` or `https`. 

**HEYTACO_ANYWHERE_HEYTACO_APP_SECRET**: Required string value provides your HeyTaco! App secret.

**HEYTACO_ANYWHERE_SLACK_CHANNEL**: Required string value provides the general slack channel to post the message. This value should be the channel id, not the name. Check [here](https://stackoverflow.com/questions/40940327/what-is-the-simplest-way-to-find-a-slack-team-id-and-a-channel-id).

**HEYTACO_ANYWHERE_HEYTACO_CLIENT_ID**: Required string value provides the client id of Slack App.

**HEYTACO_ANYWHERE_HEYTACO_CLIENT_SECRET**: Required string value provides the client secret of Slack App.

**HEYTACO_ANYWHERE_SERVICE_CLIENT_ID**: Required string value provides the client id of Github OAuth App.

**HEYTACO_ANYWHERE_SERVICE_CLIENT_SECRET**: Required string value provides the client secret of Github OAuth App.

### Step 6: Start the server

The server container can be started with the below command. The container is configured through environment variables. 

```shell
$ docker run \
  --volume=/var/lib/heytaco-anywhere:/app \
  --env=HEYTACO_ANYWHERE_SERVER_HOST={{HEYTACO_ANYWHERE_SERVER_HOST}} \
  --env=HEYTACO_ANYWHERE_SERVER_PROTO={{HEYTACO_ANYWHERE_SERVER_PROTO}} \
  --env=HEYTACO_ANYWHERE_HEYTACO_APP_SECRET={{HEYTACO_ANYWHERE_HEYTACO_APP_SECRET}} \
  --env=HEYTACO_ANYWHERE_HEYTACO_CHANNEL={{HEYTACO_ANYWHERE_HEYTACO_CHANNEL}} \
  --env=HEYTACO_ANYWHERE_HEYTACO_CLIENT_ID={{HEYTACO_ANYWHERE_HEYTACO_CLIENT_ID}} \
  --env=HEYTACO_ANYWHERE_HEYTACO_CLIENT_SECRET={{HEYTACO_ANYWHERE_HEYTACO_CLIENT_SECRET}} \
  --env=HEYTACO_ANYWHERE_SERVICE_CLIENT_ID={{HEYTACO_ANYWHERE_SERVICE_CLIENT_ID}} \
  --env=HEYTACO_ANYWHERE_SERVICE_CLIENT_SECRET={{HEYTACO_ANYWHERE_SERVICE_CLIENT_SECRET}} \
  --publish=80:8080 \
  --publish=443:8080 \
  --restart=always \
  --detach=true \
  --name=heytaco-anywhere \
  heytaco-anywhere/heytaco-anywhere:0.1
```