## Development

**Auto reload:**
```
gin -d src -x talks.db -b main -a 3001 -i
```

## Endpoints

| Request | Endpoint           | Desc                                             |
| :------ | :----------------- | :----------------------------------------------- |
| GET     | /                  | The talks homepage                               |
| GET     | /all               | Returns all former talks                         |
| GET     | /talks             | JSON of the currently visible talks              |
| GET     | /health            | Indicates how many active connections there are  |
| GET     | /ws                | Websocket endpoint                               |

**Create a new talk**
```json
{
    "type": 0,
    "name": "mirror team",
    "talktype": 0, // forum topic
    "description": "new drives for mirror",
    "week": 20220126, // YYYYMMDD optional, what day to add the talk to. empty for current week otherwise must be in the future and a Wednesday
}
```

**Hide a talk**
```json
{
    "type": 1,
    "id": 10, // talk id
}
```

**Delete a talk**
```json
{
    "type": 2,
    "id": 10, // talk id
}
```

TODO: MOVE TALKS