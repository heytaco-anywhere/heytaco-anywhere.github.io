---
title: 'Reference'
date: 2019-02-11T19:27:37+10:00
weight: 4
---

Index of server configuration settings. These configurations are injected by environment variables.

### Environment Vairables

* **HEYTACO_ANYWHERE_DEBUG**: Debug mode.

* **HEYTACO_ANYWHERE_SERVER_HOST**: Required string value configures the user-facing (and webhook) hostname. *This value is used to configure OAuth.*

* **HEYTACO_ANYWHERE_SERVER_PROTO**: Required string value provides your external protocol scheme. This value should be set to `http` or `https`. 

* **HEYTACO_ANYWHERE_HEYTACO_APP_SECRET**: Required string value provides your HeyTaco! App secret. *You can get the secret after creating HeyTaco! App* Here is the [link](https://www.heytaco.chat/team/apps/create) to create.

* **HEYTACO_ANYWHERE_WEBHOOK_SECRET**: String value provides the signing secret. *It is used to check the signature is valid or not.* It doesn't check the signature if you don't set up.

* **HEYTACO_ANYWHERE_SLACK_CHANNEL**: String value is the slack channel id. *It is used to post the message. This value should be the channel id, not the name.* Check [here](https://stackoverflow.com/questions/40940327/what-is-the-simplest-way-to-find-a-slack-team-id-and-a-channel-id).

* **HEYTACO_ANYWHERE_SLACK_CLIENT_ID**: String string value provides the client id of Slack App. *This is used to authorize access to Slack to get the access token.*

* **HEYTACO_ANYWHERE_SLACK_CLIENT_SECRET**: String string value provides the client secret of Slack App.

* **HEYTACO_ANYWHERE_GITHUB_CLIENT_ID**: String value provides the client id of Github OAuth App. *This is used to authorize access to Github to map Github users with HeyTaco! users.*

* **HEYTACO_ANYWHERE_GITHUB_CLIENT_SECRET**: String value provides the client secret of Github OAuth App.

* **HEYTACO_ANYWHERE_ATLASSIAN_CLIENT_ID**: String value provides the client id of Atlassian OAuth App. *This is used to authorize access to Atlassian to map Atlassian users with HeyTaco! users.*

* **HEYTACO_ANYWHERE_ATLASSIAN_CLIENT_SECRET**: String value provides the client secret of Atlassian OAuth App.
