---
title: 'Reference'
date: 2019-02-11T19:27:37+10:00
weight: 5
---

Index of server configuration settings. These configurations are injected by environment variables.

### Environment Vairables

**HEYTACO_ANYWHERE_DEBUG** 

Debug mode.

**HEYTACO_ANYWHERE_SERVER_HOST** 

Required string value configures the user-facing (and webhook) hostname. *This value is used to configure OAuth.*

**HEYTACO_ANYWHERE_SERVER_PROTO** 

Required string value provides your external protocol scheme. This value should be set to `http` or `https`. 

**HEYTACO_ANYWHERE_HEYTACO_APP_SECRET** 

Required slice of string value provides your HeyTaco! App secret. The server select one of secrets to issue tacos. *Secrets are separated by `,`.*

```
HEYTACO_ANYWHERE_HEYTACO_APP_SECRET=SECRET_1,SECRET_2
```

*You can get the secret after creating HeyTaco! App.* Here is the [link](https://www.heytaco.chat/team/apps/create) to create.

**HEYTACO_ANYWHERE_WEBHOOK_SECRET**

String value provides the signing secret. *It is used to check the signature is valid or not.* It doesn't check the signature if you don't set up.

**HEYTACO_ANYWHERE_SLACK_CHANNEL** 

String value is the slack channel id. *It is used to post the message. This value should be the channel id, not the name.* 

**HEYTACO_ANYWHERE_SLACK_CLIENT_ID** 

String string value provides the client id of Slack App. *This is used to authorize access to Slack to get the access token.* You can find the *Client ID* in the *Basic Information* section.

**HEYTACO_ANYWHERE_SLACK_CLIENT_SECRET** 

String string value provides the client secret of Slack App.

**HEYTACO_ANYWHERE_GITHUB_CLIENT_ID** 

String value provides the client id of Github OAuth App. *This is used to authorize access to Github to map Github users with HeyTaco! users.*

**HEYTACO_ANYWHERE_GITHUB_CLIENT_SECRET** 

String value provides the client secret of Github OAuth App.

**HEYTACO_ANYWHERE_JIRA_CLIENT_ID** 

String value provides the client id of Atlassian OAuth App. *This is used to authorize access to Jira to map Jira users with HeyTaco! users.*

**HEYTACO_ANYWHERE_JIRA_CLIENT_SECRET** 

String value provides the client secret of Atlassian OAuth App.

**HEYTACO_ANYWHERE_STORE_DRIVER** 

String value provides the driver of store. It supports `sqlite3`, `mysql`, and `postgres`. *The default value is* `sqlite3`.

**HEYTACO_ANYWHERE_STORE_SOURCE** 

String value provides the source of store. Configures the database connection string. *The default value is the path of the embedded sqlite database file.*

```
HEYTACO_ANYWHERE_STORE_SOURCE=file:sqlite3.db?cache=shared&_fk=1
```

Example mysql connection string (below). See the [official driver](https://github.com/go-sql-driver/mysql#dsn-data-source-name) documentation for more connection string details.

```
HEYTACO_ANYWHERE_STORE_SOURCE=root:password@tcp(1.2.3.4:3306)/heytacoanywhere?parseTime=true
```

Example postgres connection string (below). See the [official driver](https://www.postgresql.org/docs/current/libpq-connect.html#LIBPQ-CONNSTRING) documentation for more connection string details.

```
HEYTACO_ANYWHERE_STORE_SOURCE=postgres://root:password@1.2.3.4:5432/postgres?sslmode=disable
```

**HEYTACO_ANYWHERE_LICENSE** 

String value provides the license key. 
