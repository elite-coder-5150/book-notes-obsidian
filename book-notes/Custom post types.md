#### Post Schema

```javascript
const postSchema = new mongoose.Schema({
	title: {
		type: String,
		required: true
	},
	content: {
		type: String,
		required: true
	},
	type: {
		type: String,
		required: true,
		enum: [
			'text',
			'image',
			'video',
			'single_component',
			'component_library'
		]
	},
	imgUrl: {
		type: String
	},
	videoUrl: {
		type: String
	},

	createdAt: {
		type: Date,
		default: Date.now
	}
});

module.exports = mongoose.model('Post', postSchema)
```

#### Methods

**save()** - save a post document to the database

```javascript
const mongoose = require('mongoose');
const postSchema = require('postSchema');


```

#### Fields

1. **title** - a required string field that represents the title of the post
2. **content** - a required string field that represents the content of the post
3. **type** - a required string field the represents the type of post. This field is limited to text, image, video, single_component, and component_library
4. **imgUrl** - an optional field that represents the url of the image, if the post is of type image.
5. **videoUrl** - an otional string field that represents the url of the video, if the post is of type video.
6. **createdAt** - an options date field the represents the date and time when the post was created. This field defaults to the current date and time.

By using this schema, you can create different post and store them in a mongoDB database using mongoose. To create a post, you would first create an insnce of the post model and set its fields to the appropriate values.