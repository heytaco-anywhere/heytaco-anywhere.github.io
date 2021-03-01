---
title: 'Get started'
date: 2019-02-11T19:27:37+10:00
weight: 2
---

Let's install Heytaco Anywhere. In this example, we're going to connect Heytaco(Slack) with Github.

### Step 1: Preparation

To make Heytaco Anywhere acts on behalf of a Slack user, we have to use Slack OAuth. here is the [guide](/docs/configuration#slack) to configure Slack.

To map Slack user with Github user, we have to configure Github OAuth like the 1st step([Link](/docs/configuration#github)). 

### Step 2: Download

The Heytaco Anywhere server is distributed as a lightweight Docker image. The image is self-contained and does not have any external dependencies.

```shell
$ docker pull heytaco-anywhere/heytaco-anywhere:0
```

### Step 3: Configuration

The Heytaco Anywhere server is configured using environment variables. This article references a subset of configuration options, defined below.

* **HEYTACO_ANYWHERE_SERVER_HOST**: Required string value provides your external hostname.

* **HEYTACO_ANYWHERE_SERVER_PROTO**: Required string value provides your external protocol scheme. This value should be set to `http` or `https`. 

* **HEYTACO_ANYWHERE_HEYTACO_CHANNEL**: Required string value provides the general slack to post the message. This value should be the channel id, not the name. Check [here](https://stackoverflow.com/questions/40940327/what-is-the-simplest-way-to-find-a-slack-team-id-and-a-channel-id).

* **HEYTACO_ANYWHERE_HEYTACO_CLIENT_ID**: Required string value provides the client id of Slack App.

* **HEYTACO_ANYWHERE_HEYTACO_CLIENT_SECRET**: Required string value provides the client secret of Slack App.

* **HEYTACO_ANYWHERE_SERVICE_CLIENT_ID**: Required string value provides the client id of Github OAuth App.

* **HEYTACO_ANYWHERE_SERVICE_CLIENT_SECRET**: Required string value provides the client secret of Github OAuth App.

### Step 4: Start the server

The server container can be started with the below command. The container is configured through environment variables. 

```shell
$ docker run \
  --volume=/var/lib/heytaco-anywhere:/app \
  --env=HEYTACO_ANYWHERE_SERVER_HOST={{HEYTACO_ANYWHERE_SERVER_HOST}} \
  --env=HEYTACO_ANYWHERE_SERVER_PROTO={{HEYTACO_ANYWHERE_SERVER_PROTO}} \
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
  heytaco-anywhere/heytaco-anywhere:0
```
