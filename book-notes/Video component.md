```typescript
import { Component } from '@angular/core';
import { VideoPost } from '../models/video-post';
import { VideoService } from '../services/video.service'

@Component({
	selector: 'ng-video-post',
	templateUrl: './video-post.component.html',
	styleUrls: ['./video-post.component.scss']
})
export class VideoPostComponent {
	postedVideo: string;
	
	@Input() post: VideoPost;
}
```

```html
<div class="video-post">
	<h3>{{ post.title }}</h3>
	<p>{{ post.description}}</p>
 	<video [src]="post.videoUrl" controls></video>
 </div>

<div *ngIf="postedVideo" class="video-post">
	<ng-meta [status]="postedVideo"></ng-meta>
	<ng-comment [status]="postedVideo"></ng-comment>
</div>
```

```typescript
import { Comment } from '../models/Comment';

export interface VideoPost {
	id: string;
	timestamp: Date;
	userId: string;
	videoUrl: string;
	comment: Comment[]
}
```