---
title: Authentication
sidebar_order: 1
---

## Auth Tokens {#id1}

Authentication tokens are passed using an auth header, and are used to authenticate as a user account with the API.

```bash
$ curl -H 'Authorization: Bearer {TOKEN}' https://sentry.io/api/0/projects/
```

You can [find or create authentication tokens within Sentry](https://sentry.io/api/).

## API Keys {#id2}

{% capture __alert_content -%}
API keys are a legacy means of authenticating. They will still be supported but are disabled for new accounts. You should use **authentication tokens** wherever possible.
{%- endcapture -%}
{%- include components/alert.html
  title="Note"
  content=__alert_content
  level="warning"
%}

API keys are passed using HTTP Basic auth where the username is your api key, and the password is an empty value.

As an example, to get information about the project which your key is bound to, you might make a request like so:

```bash
$ curl -u {API_KEY}: https://sentry.io/api/0/projects/
```

{% capture __alert_content -%}
You **must** pass a value for the password, which is the reason the `:` is present in our example.
{%- endcapture -%}
{%- include components/alert.html
  title="Note"
  content=__alert_content
  level="warning"
%}

## DSN Authentication {#id3}

Some API endpoints may allow DSN-based authentication. This is generally very limited and an endpoint will describe if its supported. This works similar to Bearer token authentication, but uses your DSN (Client Key).

```bash
$ curl -H 'Authorization: DSN {DSN}' https://sentry.io/api/0/projects/
```
