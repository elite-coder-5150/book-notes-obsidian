Define a schema for the notifications table

```sql
create table `notifications`
(
	`notification_id` int(11) not null,
	`message` varchar(255) not null,
	`sender` varchar(255) not null,
	`receiver` varchar(255) not null,
	`type` enum('friend_request', 'liked', 'commented', 'mention')
		not null default 'coment',
	`status` enum('read', 'unread') default 'unread',
	`create_at` datetime not null default default_timestamp
	`updated_at` datetime not null
)
```

The following are basic queries:

```sql
-- get notification by id
select notification_id from `notifications` where notification_id >= 3

-- get notification message
select message from `notifications`
```
The code below get a notification by id

Function **getNotificationById**:



```typescript
export class NotificationController {
	deleteNotification(req, res) {
		try {
			const { id } = req.body;
	
			const sql = "delete from notifications where notification_id=?";
	
			db.query(sql, [id], (error, results) => {
				if (error) {
					console.error(error);
					res.status(500).send(error);
				} else if (results.length === 0) {
					res.status(404).send('notification not found')
				} else {
					res.status('notification deleted');
				}
			})
		} catch (error) {
			return res.status(500).send(error)
		}	
	}

	updateNotifications(req, res) {
		try {
			const { id } = req.body;
			
			const sql "update notification set read=1 where notification_id=?"
	
			db.query(sql, [id], (error, results) => {
				if (error) {
					console.error(error);
				} else {
					res.status(200).send('successfully updated notification')
				}
			})
		} catch (error) {
			return res.status(500).send(error);
		}
	}

	getNotification(req, res) {
		try {
			const sql = "
				select *
				from notifications
			";
	
			db.query(sql, (error, results) => {
				if (error) {
					console.error(error);
					res.status(500).send(error);
				} else if (results.length === 0) {
					res.status(404).send('notification not found')
				} else {
					res.status(200).send(results);
				}
			})
		} catch (error) {
			res.status(500).send(error);
		}
	}

	turnOffNotification(req, res) {
		try {
			const { id } = req.body;

			const sql "
				delete from notifications where notification_id=?
			";

			db.query(sql, [id], (error, results) => {
				if (error) {
					console.error(error);
					res.status(500).send(error);
				} else if (results.length === 0) {
					res.status(404).send('notification not found')
				} else {
					res.status(200).send(results);
				}
			})
			
		}
	} catch (error) {
		return res.status(500).send(error);
	}
}
```

```typescript
const router = express.Router();

import { deleteNotification } from '../controllers/notifications.controller';
router.delete('/notiications/:id', NotificationController.DeleteNotification);
router.post('/notification', NotificationController.CreateNotification);
router.get('/notifications', NotificationController.getNotifications)
```
The following is pseudo code for the above function

Using axios to grab the notification url 

```pseudocode
1. notification system
	1. get notifications
		1. create an sql query to select all of the notifications
		2. execute the query
			1. check to see if there are any errors
				1. if there are errors display them to the console
			2. if the length of the results is 0
				1. the notification could not be found.
			3. once those errors are resulved it then returns the results
			   and display's them in the cosole
		3. and if the try block fails the catch block is executed
	
	2. update notifications
		1. grab the id from the request
		2. create a query to update the notifications table
		3. execute the query
			1. execute the sql query
			2. interpolate the id
			3. where the id is equal to the id padded in
				1. check to see if there are any errors
					1. print them to the console
				2. and if there is no errors display a message to
				   to the console telling the user that it was successfully
				   updated
		4. and if the try block fails the catch block is executed
				   
	3. delete notifications
		1. grab the id from the request
		2. create a query to delete the notification with the specified id
		3. execute the query
			1. execute the sql query
			2. interpolate the id
			3. where the is is equal to the id passed in
				1. checks to see if there are any errors
					1. if there is an error then display a message to the 
					   console
					3. set the response to 500 and send it back to the server.
					4. if the length is zero that eans there was no 
					.  notification 
					   found.
					4. if there are no errors and the length of the results is
					   not zero then display a message to the user stating 
					   that the notification was removed from the database.
		4. and if the try block fails the catch block is executed.
	
	4. turn off notification
		1. grab the id from the request
		2. create a query that delete the notification with the specifid id
		3. execute the query
			1. interpolate the id
			2. execute the sql query
			3. check to see if there are any errors
				1. if there are errors display a message to the console
				2. if the length of results is 0, then the notification was 
				   not found.
				3. if no other errors ocurr then return the results
		4. if the try block fails, the catch block will be executed.
```

#### 1. **getNotifications()**  

This method is responsible for creating a SQL query that selects all of the notifications from the notifications table. it then executes the query. While inside the query it checks to see if there were any errors. If there were any errors they get displayed to the console. The method also check the length of the results and if it is 0, then the notifcation in question does not exist. And if there are no errors, it simply returns the results to the user.

#### 2. updateNotification()

This method is responsible for updating notifications in the notifications table. the first thing that the method does is grab the **ID** from the request. 

#### 3. deleteNotification()

This method is responsible for removing notifications form the notification table.

#### 4. turnOffNotification()

This method is responsible for turning off certain notifcation that go off too frequent.

#### added features

1. Log type system.

#### side note
The request is used when you need something from the server, and a response is what is received back grom the server