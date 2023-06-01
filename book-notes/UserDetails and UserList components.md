Tags: #angular 
```shell
ng g c user-list
```

```html
<h2>User list
<ul>
	<li *ngFor="let user of users">
		{{ user.name }}
	</li>
</ul>
```

```typescript
import { Component } from '@angular/core';

@Component({
	selector: 'ng-user-list',
	templateUrl: './user-list.component.html'
})
export class UserListComponnet {
	users = [ 
		{ name: 'John Doe' }, 
		{ name: 'Jane Smith' }, 
		{ name: 'Bob Johnson' } 
	];
}
```

```shell
ng g c user-details
```

```html
/* user-detials.component.html */
<div *ngIf="user">
	<h2>User detials</h2>
	<p>Name: {{ user.name }}</p>
	<p>Email: {{ user.email }}</p>
</div>
```

```typescript
import { Component, Input } from '@angular/core';

@Component({
	selector: 'ng-user-detials',
	templateUrl: './user-details.component.html',
	styleUrls: ['./user-details.component.scss']
})
export class UserDetailsComponent {
	@Input()user: any;
}
```

```html
<ng-user-list></ng-user-list>
<ng-user-details [user]="selectedUser"></ng-user-detials
```