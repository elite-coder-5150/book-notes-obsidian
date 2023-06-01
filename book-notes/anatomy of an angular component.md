1. **Component Decorator** - a component is defined by using a typescript class decorator with the @Component decorator. The docorator provides meta data that angular needs to create and manage the component

2. **Component Class** - the component class is a typescript class that contain the data and logic for the component. It defines properties, methods, and other functions that are used by the component's view.

3. **Component template** - the component template is the html file that defines the structure and layout of the component view. It contains placeholder for data that is bound to the component properties and methods.

4. **Component Styles** - The component styles are define the look and feel of the component. They are defined using SCSS, CSS, or any other styling language.
5. **Unit tests** - The unit test is responsible for defining test to ensure that the component is working properly and it contains all of the markup.

#### Component Decorator

The **@Component** decorator is a function that is applied to a typescript class to define it as an angular component. The decorator accepts an object that contains metadata for the component, such as the components selector, template, and style and other properties.

```typescript
@Component({
	selector: 'ng-selector-name',
	templateUrl: './simple-component.component.html',
	styleUrls: ['./simple-component.component.scss'] 
})
export class SimpleComponent {
	title: string = "this is the title";

	handleClick() {
		console.log('button clicked');
	}
}
```

In the above example, the **@Compoent** decorator defined a component name **SimpleComponent** the the selector of **ng-selector-name** can be used to include the component in an parent component's template. The template and styles defined in a separate file.

```scss
h1 {
	@include text-color(blue);
}

button {
	@include bg-color(green);
	@include text-color(white);
}
```

```html
<h1>{{ title }}</h1>
<button (ngSubmit)="handleClick()"></button>

<ng-button
	class="btn"
	[variant]="primary"
	[btnStyle]="rounded">simple button text</ng-button>
```