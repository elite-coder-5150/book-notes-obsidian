```typescript
import { Component } from '@angular/core';
import { StatusUpdate } from 'path/to/status-update.model';
import { StatusService } from 'path/to/status.service';

@Component({
  selector: 'ng-status-update',
  templateUrl: './status-update.component.html',
  styleUrls: ['./status-update.component.css']
})
export class StatusUpdateComponent {
  statusText: string;
  postedStatus: StatusUpdate;

  constructor(private statusService: StatusService) { }

  postStatus(): void {
    if (this.statusText) {
      const newStatus: StatusUpdate = {
        text: this.statusText,
        timestamp: new Date()
      };

      this.statusService.postStatus(newStatus)
	      .subscribe((postedStatus: StatusUpdate) => {
        this.postedStatus = postedStatus;
        this.statusText = ''; // Clear the input field
      });
    }
  }
}
```

```html
<ng-news-feed>
	<div class="status-update">
	  <textarea 
		  [(ngModel)]="statusText" 
		  placeholder="What's on your mind?"></textarea>
	  <button (click)="postStatus()">Post</button>
	</div>
	
	<div *ngIf="postedStatus" class="posted-status">
	  <ng-meta [status]="postedStatus"></ng-meta>
	  <ng-comment [status]="postedStatus"></ng-comment>
	</div>
	
	<div class="video-post">
		<h3>{{ post.title }}</h3>
		<p>{{ post.description}}</p>
	 	<video [src]="post.videourl" controls></video>
	 </div>
	
	<div *ngIf="postedVideo" class="video-post">
		<ng-meta [status]="postedVideo"></ng-meta>
		<ng-comment [status]="postedVideo"></ng-comment>
	</div>

	<div class="status-update">
	  <textarea 
		  [(ngModel)]="statusText" 
		  placeholder="What's on your mind?"></textarea>
	  <button (click)="postStatus()">Post</button>
	</div>
	
	<div *ngIf="postedStatus" class="posted-status">
	  <ng-meta [status]="postedStatus"></ng-meta>
	  <ng-comment [status]="postedStatus"></ng-comment>
	</div>
	
	<div class="video-post">
		<h3>{{ post.title }}</h3>
		<p>{{ post.description}}</p>
	 	<video [src]="post.videourl" controls></video>
	 </div>
	
	<div *ngIf="postedVideo" class="video-post">
		<ng-meta [status]="postedVideo"></ng-meta>
		<ng-comment [status]="postedVideo"></ng-comment>
	</div>
	<div class="status-update">
	  <textarea 
		  [(ngModel)]="statusText" 
		  placeholder="What's on your mind?"></textarea>
	  <button (click)="postStatus()">Post</button>
	</div>
	
	<div *ngIf="postedStatus" class="posted-status">
	  <ng-meta [status]="postedStatus"></ng-meta>
	  <ng-comment [status]="postedStatus"></ng-comment>
	</div>
	
	<div class="video-post">
		<h3>{{ post.title }}</h3>
		<p>{{ post.description}}</p>
	 	<video [src]="post.videourl" controls></video>
	 </div>
	
	<div *ngIf="postedVideo" class="video-post">
		<ng-meta [status]="postedVideo"></ng-meta>
		<ng-comment [status]="postedVideo"></ng-comment>
	</div>
	<div class="status-update">
	  <textarea 
		  [(ngModel)]="statusText" 
		  placeholder="What's on your mind?"></textarea>
	  <button (click)="postStatus()">Post</button>
	</div>
	
	<div *ngIf="postedStatus" class="posted-status">
	  <ng-meta [status]="postedStatus"></ng-meta>
	  <ng-comment [status]="postedStatus"></ng-comment>
	</div>
	
	<div class="video-post">
		<h3>{{ post.title }}</h3>
		<p>{{ post.description}}</p>
	 	<video [src]="post.videourl" controls></video>
	 </div>
	
	<div *ngIf="postedVideo" class="video-post">
		<ng-meta [status]="postedVideo"></ng-meta>
		<ng-comment [status]="postedVideo"></ng-comment>
	</div>
</ng-news-feed>
```

```typescript
export interface StatusUpdate {
	id: string;
	text: string;
	timestamp: Date;
	userId: string
	comments: Comment[]
}

export interface Comment {
	id: string;
	text: string;
	timestamp: Date;
	userId: string
}
```