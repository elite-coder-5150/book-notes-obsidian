
In Angular, you can interact with backend apis by using the **HttpClient** service. The **HttpClient** service provides a simple way to make http requests to your backend api and receives their responses.

1. **Create a server to interface with your backend api** - you can use the angular cli to generate a new service.

```shell
ng g s services/api
```

2. **In the service the HttpClient** - servcice and use it to make http requests to your back end api

```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';

@Injectable({
	providedIn: 'root'
})
export class ApiService {
	private baseUrl = 'http://localhost:5000'
	constructor(private http: HttpClient) {}

	getUsers() {
		return this.http.get(`${this.baseUrl}/users`)
	}

	createUer(user: any) {
		return this.http.post(`${this.baseUrl}/users`, user);
	}

	updateUser(id: number, user: any) {
		return this.http.put(`${this.baseUrl}/users/${id}`, user);
	}

	deleteUser(id: number) {
		return this.http.delete(`${this.baseUrl}/users/${id}`)
	}
}
```

```typescript
import { Component, OnDelete, OnInit } from '@angular/core';
import { ApiService } from '../services/api.service';

@Component({
	selector: 'ng-user-list',
	templateUrl: './user-list.compoennt.html',
	styleUrls: ['./user-list.component.scss']
})

export class UserListComponent implements OnDelete, OnInit {
	users: any[];

	constructor(private api: ApiService) {}

	ngOnInit() {
		this.api.getUsers().subscribe((users: any[]) => {
			this.users = users
		});
	}

	createUser(user: any) {
		this.api.createUser(user).subscribe((newUser: any) => {
			this.users.push(newUser)
		});
	}

	deleteUser(id: number) {
		this.api.deleteUser(id).subscribe(() => {
			this.users = this.users.filter(u => u.id !== id);
		});
	}

	updateUser(id: number, user: any) {
		this.api.updateUser(id, user).subscribe(() = {
			const index = this.users.findIndex(u => u.id === id);
			this.users[index] = user;
		});
	}
```

In the code above, the **UserListComponent** compoent uses the **ApiService** service to retrieve user data from the backend api and update the user data as needed. The component subscribes to the **Observable** returned by the service methods to receive the api response

By using the **HttpClient** service for interacting with your backend api, you can create powerful and dynamic web apps.

#### implementing navigation and routing

```typescript
import { NgModule } from '@angular/core';
import { Routes, RouterModule } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';
import { ContactComponent } from './contact/contact.component';

const routes: Routes = [
	{
		path: '',
		component: HomeComponent
	},
	{
		path: 'about',
		compoent: 'AboutComponent'
	},
	{
		path: 'contact',
		component: ContactComponent
	}
]

@NgModule({
	imports: [RouterModule.forRoot(routes)],
	exports: [RouterModule]
})
```

```html
<nav>
	<ul>
		<li><a routerLink="/">home</a></li>
		<li><a routerLink="/about">about</a></li>
		<li><a routerLink="/contact">contact</a></li>
	</ul>
</nav>
```