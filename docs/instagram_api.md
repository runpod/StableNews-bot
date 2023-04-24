Followed the following tutorial to get the API working: https://levelup.gitconnected.com/automating-instagram-posts-with-python-and-instagram-graph-api-374f084b9f2b

## 1 - Generate API access token

This will generate a shot lived access token that can be used to generate a fb_exchange_token.

Required:

- App ID
- App Secret

```BASH
curl -X GET "https://graph.facebook.com/oauth/access_token
  ?client_id={your-app-id}
  &client_secret={your-app-secret}
  &grant_type=client_credentials"
```

Alternatively `&access_token={your-app_id}|{your-app_secret}`

## 2 - Generate token with longer life

```BASH
curl -i -X GET "https://graph.facebook.com/{graph-api-version}/oauth/access_token?
    grant_type=fb_exchange_token&
    client_id={app-id}&
    client_secret={app-secret}&
    fb_exchange_token={your-access-token}"
```
