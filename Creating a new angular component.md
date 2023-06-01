
```shell
ng g c component-name
```

When creating component in angular, There is a few things that you may want to keep in mind. Use meanful component name that is descriptive. For instance:

```shell
ng g c status-update
```

What then command generated

```pseudocode
status-update.component.html
status-update.component.ts
status-update.component.scss
status-update.component.spec.ts
```

```typescript
@import { Component, OnInit } from '@angular/core';

@Component({
	selector: 'ng-status-update',
	teamplateUrl: './status-update.component.html',
	styleUrls: ['./status-update.compoent.scss']
})
export class StatusUpdateComponnet implements ngOnInit {
	title: string = 'simple title';
	ngOnInit(): void {
	
	}
}
```

```typescript
@Component({
	selector: 'ng-video-post',
	template: './video-post.component.html',
	styleUrls: ['./video-post.compoennt.scss']
})
export class VideoPostComponent implements OnInit {
	ngOnInit(): void {
	
	}
}
```

```html
<ng-newsfeed>
	<ng-status-update></ng-status-update>
	<ng-video-post></ng-video-post>
</ng-newsfeed>
```

```shell
ng g c news-feed
```

```typescript
import { Componet, OnInit } from '@angular/core';

@Component({
	selector: 'ng-news-feed',
	templateUrl: './news-feed.compoennt.html'
	styleUrls: ['./news-feed.compoennt.scss']
})
export class NewsFeedComponent implements OnInit {
	ngOnInit(): void {
		const posts = axios.get('/user/user_id/news_feed')
	}
	onVideoPost() {}
	onStatusUpdate() {}
	onImgPost() {}
	onComponentPost() {}
	onComponentLibraryPost() {}
}
```

#### Features I would like to add to ever post.

1. add the meta information about the post after every posting from thie user
2. implement functionality that allows users to leave command on postings after the user has pade the post
3. and insert the commenting functionality with the meta infomation after every post the user makes.

#### Key information for the meta

1. number of likes
2. number of views
3. number of shares
4. number of commands

#### Key information of comments

1. the ability to mention another user
2. mention another post
3. react to a commant or a post
	1. reactions include
		1. like
		2. dislike
		3. agree
		4. disabrove of
4. popular comments
5. comment data
	1. number of replies
	2. number of interactions
		1. likes
		2. loves
		3. dislikes
	3. have the most popular at the top of the list.

#### Key infomation of messages

1. public chat messages
2. private chat messages with the ability to block any from private messaging.
3. total message count in words.
4. the main users messages are on the right
5. and the incoming messages are always on the left.

#### Key information of notifications

1. user sending notification
2. type of notification
3. description of the message
4. if its more than 24 hours old, simple return the date it was bosted.
5. date format: day of week, day_of_month, month, year.

#### key features of the generate video id

1. use a-z and A-Z and number 0-9
2. it has to ben in a 10 digit number when generated

#### key features of the user id generator

1. use a-z, A-Z, number 0-9
2. it has to be in a 12 digit number when the final number is generated.

