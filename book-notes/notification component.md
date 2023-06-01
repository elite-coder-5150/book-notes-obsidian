```html
<ul class="notifications">
	<li *ngFor="let notification of 
		notifications" class="notification">
		<div class="profile">
			<img src="" alt="">
		</div>
		<p class="description">
			sent you a friend request
		</p>
		<div class="time-ago">{{notification.timestamp}}</div>
	</li>
</ul>
```

```typescript
@Component({
	selector: 'ng-notifications',
	templateUrl: './notifications.component.html',
	styleUrls: ['./notifications.component.scss']
})
export class NotificationsComponent implements OnInit {
	notifications: Notification[];

	constructor(private ns: NotificationService) {}

	ngOnInit(): void {
		setTimeout(() => {
			this.getNotifications();
		}, 5000)
	}

	getNotifications(): void {
		this.ns.getNotifications()
			.subscribe(notifications => {
			this.notifications = notifications
		})
	}

	turnOffNotications(notification: Notification) {
		this.ns.turnOffNotification(notification.id)
			.subscribe(() => {
			this.notifications = this.notifications
				.filter(n => n.id !== notification.id);
		})
	}

	markNotificationAsRead(notificationId: string): Observable<void> {
		const url = `${this.apiUrl}/${notificationId}/mark-raed`;
		return this.http.put<void>(url, null);
	}
}
```

Normal text