# DiscordSweep
Nuke or overide your Discord account's messages.

# Filters
- Date
- Server
- To (in the case of private messages)
- Channel

# Steps
1. Get a list of servers and their IDs
- Parse HTML of the electron app `/channel/[sumnumbershere / serverid]`
2. Search for all messages by a user in the server
`GET` `/guilds/{server.id}/messages/search?author_id={user.id}&offset={offset}` >> `200`
3. Delete the messages
`DELETE` `/channels/{channel.id}/messages/{message.id}` >> `204`

# Notes
- Rate limit returns HTTP 429


