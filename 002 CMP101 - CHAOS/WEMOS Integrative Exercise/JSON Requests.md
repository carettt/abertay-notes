[[2022-11-07]], 15:55
Type: #information
Tags: [[Web Development]], [[JSON]],  [[Backend Development]]

# JSON Requests

Example Request for formatting  requests from clients to servers:
```json
{
	"timestamp": "[timestamp]",
	"messageID": "[messageID]",
	"message": "[encrypted]",
	"userID": "[userID]",
	"reply": {
		"isReply": "true",
		"replyID": "[messageID of reply]"
	}
}
```

Database Structure

```json
{
	"users" : {
		"jsmith": {
			"displayName": "Jerry Smith",
			"contacts": ["bsmith", "msmith"]
		},
		"bsmith": {
			"displayName": "Beth Smith",
			"contacts": ["msmith"]
		},
		"msmith" : {
			"displayName": "Big Mort",
			"contacts": []
		}
	},
	"groups": {
		"uniqueIDChat": {
			"chatName": "Parents chat",
			"members": ["bsmith", "jsmith"],
			"messages": [
				{"id": "jsd9fad97g24h", "sender": "bsmith", "message": "dammit jerry i told you to do homework with morty", timestamp: 19283981}
			]
		}
	}	
}
```

---

## References