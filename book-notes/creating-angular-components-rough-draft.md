
Tags: #angular 

<hr>

#### Component Modularity

Component modularity referes to the practice of oganizing and designing software components in a way that promote reusability, maintainability, and separation of concerns. It involves breaking down the application into smaller, self-containing component taht be be developed, tested and maitained identpendently.

Modular components have a singlular responsibility, focusing on specific tasks or functionalities. They should ideally have a clear and well-defined purpose, makeing it easier to undersntand and maintain. By adhering to the principle of singlular responsibility, componet become more reusable and adaptable to different parts of the application.

Component modularity also promotes component reuse, where components can be utilized in multiple partos of the application or even in different projects. This reusability reduces duplocation of code and efforts, leading to imporved productivity and consistency.

To estabilish modularity, it essential to estabilish a compoennt hierarch that defiens the reslationships and dependencies between componentss. Components should be structured in a heirarchical manner, with higher-level components componed of lower-level components. This heirrchy help maintain clear and organized structure for the application.

In addition to these principles, component modularity can also enhance by defined input and output properties for for compoentns. These properties estabilish well-defined interfaces through which compoentns can communication and share data.

#### Singular responsibility

The principle of singular responsibility emphasizes that each component should have a clear and distinct purpose, focusing on a single task or responsibility. It advocates for components to be designed to excel at one specific function, allowing for modular and maintainable code. This principle ensures that modifications made to a component have limited impact on other parts of the application, reducing unintended side effects and promoting code stability.

#### Component Reuse

Component reuse involves utilizing a component in various contexts or applications. Reusable components provide developers with the opportunity to save time and effort by utilizing existing functionality instead of starting from scratch. It is essential to design reusable components that can be effortlessly integrated into different systems without the need for extensive modifications. This approach streamlines development processes and promotes efficiency by leveraging pre-existing components.

#### Component Hierarchy

Component hierarchy involves structuring components in a hierarchical manner, with higher-level components encompassing and interacting with lower-level components. This organization helps manage the complexity of an application by providing abstraction and coordination. Higher-level components handle broader functionalities and delegate specific tasks to lower-level components. This hierarchical arrangement enables better organization, reusability, and maintainability of components within the application.

#### Component composition

Component composition is the process of combining smaller self-contains compoents to create large and more itricate components or systems. This componsition can be accomplished through different mechanisma, including nesting componetns within each other, utilizingcompoennt connetiors, or employing dependinncy injection techniques.

By componsing components, developers can create more powerful and versital component by asseembling smaller, rusable bluilding blocks. This promotes reusability, as the same components can be used in different context or applications. It also enhandes maintainability, as smaller comonetns are easier to understand, test and update independently.

Component composition contributes t scalability, as it allows for the creation of complex systems by assemblish and reushing smaller components. It foters a modulear architecture where components can be developed and maintained idenpendently, leading to more flexibile and adpative systems.

Overall, component composition plays an crucial in deesigning softwar archietictutess that are modulear, resuable and scalable. It promotes code organization and facilittess development of compext system with ease.

#### Input and output properties

Input and output properties are a way for components to communicate and share data with each other in Angular.

Input properties, also known as input bindings, allow a parent component to pass data to its child component. By defineing an input proeprty in a child compoent, the parent component can bind a value to that property when using the child component in its template. The child component can then access and use that value. This enabled the parent component to prvide dynamic data or configuration to the child component.

Here is an example of how input property is defined in a child comonent:

```typescript
@Input() data: any;
```

In the above code, the **data** property is marked as an input property using the **@Input()** decorator. The parent component can bind a value to this property using peropty binding syntax in its template.

Output properties, on the other hand, allow the child component to emit events or pass data back to tits parent component can listen to and respond to. This facilitates communications and interaction between the parent and child components.

Here is an example of an output property is defined in a child component:

```typescript
@Output() event: EventEmitter<any> = new EventEmitter<any>()
```

In the code above, The **event** property is marked as an output prooperty by using the **@Output()** decprator. The child component can emit events or values through this property using the **emit** method of the **EventEmitter** class. The parent component can then listen to those events and take appropriate actions.

Using Input and output properties, components can easily exchange data and communicate with each other, enabling the building of flexible and reusable component-based architectures.

#### Component Services

Component services are a way to encapsulate and provide shared functionality, data, or business logic to components in Angular. Services act as a central point of communication and coordniation between componets, allowing them to acess common resources and perform shared operations.

Component services are typically defined as injectable classes using the **@Injectable()** decorator. These services can be provided at the component level or at a hight level, such as the module level, to ensure that all componets within a spcific scope have access to the same instance of the service.

Some common use cases for component services include;

1. **Data sharing** - services can be used to share data between components. For instance, a service can fetch data from an api and store it, allowing multiple componets to acess and manipulate the data.

2. **Business Logic** - services can encapsulate complex business logic that is used by multiple components. This helps avoid code duplication and promotes code reuse.

3. **External integrations** - Services can handle interactions with external APIs, libraries, or services. They can encapsulate th elogic required for authentication. API requests, data transformations, and error handling.

4. **Event communication** - Services can act as an event bus or message broker, allowing components to subscribe and publish events. This emables loose coupling between compoennts, as the can commuiction indirectly through the service.

5. **State management** - Services can manage and maintain application state. They can hold and update shared state variables, allowing compoennt to access and modify the state as needed.

By using componet services, developers can create more modular, maintainable, and testable code. Services promote separation of concerns by separating business logic from component implementation. The also facilitate code resuability and promote a more scalable architecture.

#### Lazy loading

Lazy loading is a technique used in software developement, particularly in web applications, to optimie the initial loading time and improves performance by deferring the loading of certain resources or modules until they are actually needed. Instad of loading the entire aplication or all its modules at once, lazy loading only load the necessary parts on-demand, reducing the initial payload and improve the user experennce.

In the context of Angular, lazy loading is a feature provided by the Angular Router. It allows you to load modules or componets asyncrhously when a specific route is accessed. By defining routes with lazy loading., Angular can split the application into smaller bundles that are loaded when the user navigates to a specified route.

Lazy loading is beneficial in several ways:

1. **faster initial load time** - by loading only the essential component or modules on the initial page looad, the application can start faster and improve the perceived performance.

2. **Reduces payload** - Lazy loading help in reducing the initial payload by loading only the required resources for a specific route. This can significantly imporove the application's loading time, especialy for larger applications

3. **Improved performance** - By loading components or modules on-demand, the overall performance of the application can be improved as unneessary resources are not loaded upfront. This leads to faster trendering and better user experence.

4. **Code organization** - Lazy loading encourages modularization and better code organization by separating features into its own modules. Each module can be loaded independently, making it easier to manage and maintain the codebase.

To implement lazy loading in an Angular application, you defined routesw with the **loadChildren** property in the Angular Route configuration. This peroperty specifies the path of the module or component that should be loazily loaded when the corresponding reoute is accessed.

Lazy loading is particularly useful in applications with compilex features sets, large codebases, or when dealing with large amounds of data. It allows you to optimize performance and primove the overal user expereince by loading resources and modules only when they are needed.

#### Directory structure

The directory structure refers to the organization and arrangement of files and folders within a project.

```pseudocode
src - this is the root directory of the application's source code
	app - this directory contains the main appliction
		components - this directory holder the individual components of the 
		app.
		services - this directory contains the services used by the app,
		modules - this directory is used for organizing features modules
		shared - this directory contains sared components, directives, pipes, 
		and other utility files.
		assets - this directory is used for storing static assets such as 
		images, fonts, or configuration files.
		styles - this directory contains the global styles used throughout 
		the application.
		app-router.module.ts - this file defines the routing configuration 
		for the application.
		app.component.ts - this file contains the root component of the 
		application.
		app.module.ts - this file is responsible for bootstrapping and
		configuring the application module.
	envoronments - this directory contains environment specific configuration
	files.
```

This is the basic structure, and it can be expanded or modified based on the neds of the project. It's important to maintain a logical and consistent organization of the file and folders, ensuring that similar files are grouped together and that the structure is easy to understand and navigate.

A well designed directory structure promotes code readibility, and maintainability. It helps teams collaborate effectively and factilates the separation of concerns within the appllication. It's recommended to follow estabiliahed best practices and conventions, while also considering the specific requirements and complexities of the project.

#### Input and Output.

Input and output are important concept in comonent-based frameworks like Angular. They enable communication and data flow between components

#### Input properties

- input properties, also known as input bindings, allow data to be passed from a parent component to a child component. By defineing an input property in the child component, the parent compnent can bind a value to that property in the template where teh child component is used. This allows the child component to consume and use the data provided by the parent componet. Input properties are decorated with the **@Input()** decoractor in Angular.

#### Output properties

- Output properties, also known as output bindings, enable child components to emit events or send data back to its parent component. By defining an output peroperty in the child component and using an **EventEmitter** to emit events or values, the parent component can listen to these events and respond accordingly. Output propertes are decorated with the **@Output()** decorator and use an **EventEmitter** to emit events or generate data.

The combination of input and output properties allows for the building of flexibleand reusable componets that can communicate and share data with their parent and child components.

Parent Component:

```typescript
import { Component } from '@angular/core';

@Component({
	selector: 'ng-parent',
	templateUrl: './parent.component.html',
	styleUrls: ['./parent.component.scss']
})
export class ParentComponent {
	message: string = 'hello from parent';

	handleEvent(data: string) {
		console.log('received event from child', data)
	}
}
```

```html
<h1>Parent Component</h1>
<ng-child [message]="message" (event)="handleEvent($event)"></ng-child>
```

Child Component

```typescript
import { 
	Component, 
	Input, 
	Output,
	EventEmitter 
} from '@angular/core';

@Component({
	selector: 'ng-child',
	templateUrl: './child.component.html',
	styleUrls: ['./child.component.scss']
})
export class ChildComponent {
	@Input() message: string;
	@Output() event = new EventEmitter<string>();

	emitEvent() {
		this.event.emit('event data from child')
	}
}
```

```html
<h2>Child component</h2>
<p>{{ message }}</p>
<button (click)="emitEvent()">Click me</button>
```

In the above code, the parent component passes the **message** property to the child component through the input binding. the child component displays the value of ** message in its template.

The child component also emits an event using the output binding. The parent componet listens to this event and invokes the **handleEvent** method when it is triggered.

This demonstrates how input and output properties facilitate the exchange of data and events between components, allowing for flexible and interactive component-based architecture.

#### Event Emitters

Event emitters in angular are mechanism for components to emit custom events that other components can subscribe to and respond accordingly. Event emitters are typically used to facilitate communications and interation between parent and child components or between sibling components.

To use event emitters in Angular, follow these steps:

1. import the **EventEmitter** class and **Output** decorator from **@angular/core**:

```typescript
import { EventEmitter, Output } from '@angular/core';
```

2. Declare an instance of **EventEmitter** in your component class, specifying the type of data that will be emitted:

```typescript
@Output() simpleEvent = new EventEmitter<string>();
```

In the example above, I created an event emitter called **simpleEvent** that will emit strings.

3. Emit the event whenever it need to be triggered using the **emit** method of the event emitter class.

```typescript
this.simpleEvent.emit('Event data');
```

The above code emits the event with the specified data, which ca be any value of sepcified type.

4. In the component template where you wnat to listen to the event, use the event binding syntax to subscribe to the event and execute a method when it is triggered:

```html
<ng-child (simpleEvent)="handleEvent($event)"></ng-child>
```

In the above code, I simple binded the **singpleEvent** event to the child component to the **handleEvent()** method of teh parent component. The **$event** varaible represents the emitted event data.

5. Implement the method in the parent component to handle the emitted event:

```typescript
handleEvent(data: string) {
	console.log('received event', data)
}
```

The **handleEvent** method will be called whenever the **simpleEvent** event is emitted, and it will receive the event data as a parameter.

By using event emitters, components can communicate and exchange data in a decoupled manner, enabling loose coupling and reusability. Event emitters provide a flexible and powerful way to implement custom event driven behavior in Anguar applications.


#### Service communication

1. create a shared service

```typescript
import { Injectable } from '@angular/core';
import { Subject } from 'rxjs';

@Injectable({
	providedIn: 'root'
})
export class DataService {
	private dataSubject = new Subject<string>();
	dataObs = this.dataSubject.asObservable();

	sendData(data: string) {
		this.dataObs.next(data)
	}
}
```

In the code above, I defined the **DataService** with a private **dataSubject** of type **Subject** of type string. The **dataObs** property exposes an observable that components can subscribe to recieve data. The **sendData()** method is used to emit new data to the observable subscribers

2. inject the service into the components that need to communicate:

```typescript
import { Component } from '@angular/core';
import { DataService } from '../services/data.service';
@Component({
	selector: 'ng-sender',
	templateUrl: './sender.component.html',
	styleUrls: ['./sender.component.scss']
})
export class SenderComponnet {
	constructor(protected ds: DataService) {}

	send() {
		this.ds.sendData('hello from sender')
	}
}
```



```html
<button (click)="send">send data</button>
```

```typescript
@Component({
	selector: 'ng-receiver',
	templateUrl: './receiver.component.html',
	styleUrls: ['./receiver.component.scss']
})
export class ReceiverComponent {
	receivedData: string;

	constructor(private ds: DataService) {
		this.ds.dataObs.subscribe(data => {
			this.receivedData = data
		})
	}
}
```

In the **SenderComponent**, I injected the **DataService** and call **sendData()** method to emit the data.

In the **ReceiveerComponent** i injected teh **DataService** and subscrib to the **dataObs** observable to receive the emitted data.

With this setup, when the **send()** method in the **SenderComponent** is called, it triggers the **sendData()** method in the dataservice, which emits the data trhough the dataObs observable. The **ReceiverComponent**  subscribes to the observable and receives the emitted data, updating the received data property.

By Using a shared service for communcation, components can exchange data or trigger actions without thaving direct dependencies on each other. This promotes loose coupling, reusablity, and a separation of concertns between componets.

#### Local references and ViewChild

1. Local reference provides a way to reference elements or components in the template using a variable name. You can use the hash **#** symbol followed by the name to create a local reference.

```html
<input #simpleInput type="text">
<button (click)="logValue(simpleInput.value)">Log value</button>
```

2. **ViewChild** - the **ViewChild** decorator allows you to access a child component, element, or directive in the component class. It provides a programmatic way to interact with sepcific elements or component within the template.

```html
<ng-child></ng-child>
```

```typescript
import { Component, ViewChild } from '@angular/core'
import { ChildComponent } from '../child-component/child.component'

@Component({
	selector: 'ng-parent',
	templateUrl: './parent.component.html',
	styleUrls: ['./parent.component.scss']
})
export class ParentComponent {
	@ViewChild(ChildComponent) childCompoonent: ChildComponent;

	callChildMethod() {
		this.childComponent.childMethod();
	}
}
```

```html
<ng-child></ng-child>
<button (click)="callChildMethod()">call child method</button>
```

In the code above, the **ViewChild** decorator is used to obtain a reference t the **ChildComponent** in the **ParentComponent** class. The **callChildMethod()** method can then be used to call methodsor access properties of the child component.

```html
<ng-child #simpleChild></ng-child>
```

```typescript
import { Component, ViewChild } from '@angular/core';
import { ChildComponent } from './child.component';

@Component({
  selector: 'app-parent',
  template: `
    <child-component #myChild></child-component>
    <button (click)="callChildMethod()">Call Child Method</button>
  `,
})
export class ParentComponent {
  @ViewChild('myChild') childComponent: ChildComponent;

  callChildMethod() {
    this.childComponent.childMethod();
  }
}
```

in this case, **ViewChild** references the child component using the local reference #simple-child 

Local references and **ViewChild** provide ways to access and interact with element  and components in the template form the component class, allowing for more dynamic and interactive behaviro in angular applications.

#### RxJs Observables

RxJs is a powerful library for reactive programming in javacript, and is heavily used in angular for handling asynchronous operations and event-based programming. Observables are a fundamental concept in RxJs and are used to represent sequqnces of values over time.

Observable in RxJs:

- Observables are objects that emit values over time, and other parts of you application can subscribe to those values.

- Observables can emit multiple values asynchronously and can be used to represent various data sources, such as user input HTTP responses, or timer events.

- Observables provide a set of ooperations that allow you to transform, filter, combine, and handle the emitted value in a declarative and composable way.

- Observables follow the Observer pattern, where they have three main role: the source that emits values, the subscriber that consumes the emitted values, and the subscription that represents the connecteion between the source and subscribers.

```typescript
import { Component } from '@angular/core';
import { Observable } from 'rxjs';

@Component({
  selector: 'app-example',
  template: `
   
  `,
})
export class ExampleComponent {
  values: number[] = [];

  startObserving() {
    const observable = new Observable<number>((observer) => {
      let count = 0;
      const intervalId = setInterval(() => {
        observer.next(count);
        count++;
      }, 1000);

      return () => {
        clearInterval(intervalId);
      };
    });

    const subscription = observable.subscribe((value) => {
      this.values.push(value);
    });

    setTimeout(() => {
      subscription.unsubscribe();
    }, 5000);
  }
}

```

```html
<button (click)="startObserving()">Start Observing</button>
<ul>
	<li *ngFor="let value of values">{{ value }}</li>
</ul>
```

in the code examples above, I created an Observable that emits a sequences of numbers every second. When the start observing buttin is clicked, the subscribtion is created, and the emitted values are pushed into the **values** array, which is then rendered in the template using the **ngFor**.

After 5 seconds, I then call **subscription.unsubscribe()** to stop receiving futther  values. on the subscription object.

Observables provide a powerful way to handle asynchronous and event-based programing in angular. They allow you to handle and transform data stream in a reactive and declarative maner, proving a clean and concise way to handle complex scenarios.

#### Angular router

Angular Router is built-in routing library providing angular that enabled nav igation and routing wiin an angular application. it allows you to define routes, map them to components, and handle navigation between different views in a single page application.

#### key features of angular router:

1. **Router configuration** - you can define routes and their associated components using the **RouterModule.forRoot()** method in the application root module. Routes are defined as an array of route objects with properties such as path, compnent and additional configuration options.

2. **Route parameters** - Angular router supportes route parameters, allowing you to define dynamic segments in the route path. Parameters can be accesssed in the component using the **ActivatedRoute** service.

3. **Nested routes** - you can define nested routes to create heirachical navigation structures. Child routes are configured witin the component that seres as the parent route.

4. **Route guards** - angular router provides routes guards, such as **CanActivate**, **CanDeactivate**, **CanLoad**, and **Resolve**, to control access to routes and performas tasks before or after route activation.

5. **Lazy loading** - Angular router supports lazy loading, which allows you to laod modules and components on-demand as the user navigates to specific routes. This helps improve  application performance by reducing the initial loading time.

6. **Router link** - The **routerLink** directive allows you to create navigation links within tempaltes. it generates approprates links based on  the route configuration, eliminating the need for manually constructing the URLs

7. **Router events** - The router emits various events during navigation, such as **NavigationStart**, **NavigationEnd**, and **NavigationError**. You can subscribe to these events to perform actions based on the navigation lifecycle.

8. **Router resolvers** - Angular router provides routes resolvers, allowing youi to fetch data before activating a routes. Resolves are function that execute before the route is activated, ensuring the necessary data is available win the component is initialized.

Overall, the router that is built-in to Angular simplifies the implementation of navigation and routing in Angular applications. It provides a structured and declarative approach to handle navigation between views, router parameter handling, route guards, lazy loading and other advance routing features.

#### Use ngIf and ngSwitch wisely

When using the **ngIf** and **ngSwitch** directives in angular template, its important to use them wisely to ensure efficient rendering and maintainable code. Here are some guidelines for using **ngFor** and **ngSwitch** effectively.

1. **ngIf** directive
	- Use **ngIf** to conditionally render elements or components based on bollean expressions.
	
	 - avoid complex or heavy compultations within **ngIf** expression. Compute the value in the component and bind it to a variable for better performance.
	 
	- If you need to conditionally show or hide multiple elements, consider grouping them within a container element and applying **ngIf** to the container instead of each individual element.
	 
	- Avoid nesting multiple **ngIf** directives. If possible combine conditionals into a single expression.
	
	- Be mindful of potential side effects. Understand that elements within an **ngIf** block will.be destroyed and recreated when the condition changes.

2. **ngSwitch** directive
	1. use **ngSwitch** when you have multiple cases to evaluate and render different content based on the evaluated  value.
	
	2. Prefer **ngSwitch** over multiple **ngIf** statements when the number of cases is relatively large.
	
	3.  keep the **ngSwitch** expressions simple and avoid complex computations. Compute the value in the compnent and bind it to a variable if needed.

	4. use **ngSwitchDefault** to define a default case when none of the **ngSwitchCase** condition match.

#### General tips

1. Use **ngIf** and **ngSwitch** sparingly. Overusing them can lead to complicated templates and reduce maintainability.

2. consider using other structured directives like **ngFor** or custom structual directives when appropriate.

3. Keep the template code clean and readable. Use indentation and proper formatting to enhance code readability.

4. Consider extracting complex logic or repetitive code into separate methods or functions witin the component class for better code organization and maintainability.

By using **ngIf** and **ngSwitch** judiciously and following these guidelines, youi can create template that are more efficient, maintainable, and easier to understand.

#### Use trackBy for ngFor

When using the **ngFor** directive in angular templates, its recommended to use the **trackBy** function allows angular to track the identity of each item in the iterable and determine when changes occur.

Here' show yo ucan use **trackBy** with **ngFor**:

1. define a unique identifier for each item in the iterable. This identifier can be a property of the item or a general id.

2. in the component class, create a method that take the index of the item as arguments and returns the unique identifier. This method will be used by the **trackBy** function.

3. in the template, user the **trackBy** option with the **ngFor** directive and bind it to the **trackBy** function

Here's an example:

```typescript
export interface Item {
	id: number,
	name: string
};
```


```typescript
import { Item } from '../models/item.ts';

@Component({
	selector: 'ng-sample',
	templateUrl: './sample.component.html',
	styleUrls: ['./sample.component.scsss']
})
export class SimpleComponent {
	items Item[] = [
		{ id: 1, name: 'item 1' },
		{ id: 2, name: 'item 2' },
		{ id: 3, name: 'item 3'}
	];

	trackById(index: number, item: Item): number {
		return item.id;
	}
}
```

In the code above, the **trackById** method returns the **id** property of each item as a unique identifier. The **trackBy** option is then used in the **ngFor** directive, binding it to the **trackById** method.

By using the **trackBy**, Angular can efficiently update the DOM by reusing existing elements when the identity of thits doesn't change. This results in improved performance, expecaiily when wroking with large lists or when itms are added, removed or re-ordered frequently.

It's important to note that the **trackBy** function should return a unique identifier and shouldnot change for the same item throughout its lifetime. It's recommended to use a property that is immutable or a unique identifier that remains constant.

Here's the template:

```html
<ul>
	<li *ngFor="let item of items; trackBy: trackById">
		{{ item.name }}
	</li>
</ul>
```

#### Avoid excessive template bindings

In Angular, template bindings are used to bind data and handle events in the template code. While angular's template syntax is powerful and flexible, its important to avoid excessive  template bindings to keep your code clean and maintainable. Here are some tips to acheive this:

1. Use property binding instead of event binding when approprate: 
	1. property binding **[property]="expression"** is generally simpiler and more readable than event binding
	
	2. event binding **(event)="handler()"** Whenever possible, favor property binding to pass data from the component to the template.

2. Limit the complexity of template expressions: Avoid placing complex logic or calculations directly within template expression. Indead move such logic to the component class and expose simpiler properties or method that can easily bound to the template.

3. Break down complex tempalte into smaller componets. If you template becomes too large or contains multiple layers of nesting, consider breaking it down into smaller reusable components. This not only improves maintainability by talso reduces the number of template bindings required.

4. Utilize angular directives and pipes: Angular provides built-in directive and pipes to handle common scenarios. take advantage of these features to timplify you template and reduced the need for explicit bindings. For instance, the **ngFor** directive can eliminate the need for explicit iteration bindings in many cases.

5. Avoid excessibe two-way binding - Two-way data binding [(ngModel)] can make template more concise but can also indtroduct complexities and make it harder to track data flow. Use twoway binding sparingly andprefer on-way data binding when event binding when possble.

6. Use template reference varables judiciously - Template reverence variables can be useful to referent elements or cmponets witin templates. However, excessive use of these variables can clutter the template and make it harder to understand. use them judiciously and oinly when necessary.

7. Consider reactive forms - Angular reactive forms provide declarative way to manage form data and validation. By utilizing reactive forms, you can reduce the need for explicit template bindings related to form handling

Remember that the goal is to strike a balance between code readability and functionality. By avoiding excessive template bindings and follow best practices, you can write clean and maintainable angular template that are easier to understnad and modify over time.

#### Limit DOM manipulations in Angular

Limiting DOM manipulations in Angular is essential for improving performance and maintaining a clean codebase. Here are some tipe to help you acheive that:

1. use angular's data binding - angular's data binding allows you to bind data directly to DOM elements without manually manupulating the DOM. Take advantage of property binding and event binding to update and handle changes in the template.

2. Use **ngIf** and **ngSwitch** instead of manipulating the DOM - instead of manually manipulating the DOM to show or hide elements based on conditions, utilize Angular structure directive **ngIf** and **ngSwitch**. These directives conditionally render or remove elements from the DOM, ensuring efficient and automatic updates.

3. Leverage **ngFor** for list rendering - When iterating over a collection to render a list of items, use the **ngFor** driective instead of manually manipulating the DOM. **ngFor** automatically handles adding and remove elements based on the collection changes, optimizing rendering process.

4. Utilize **ngClass** and **ngStyle** for dynamic styling - instead of manipulating the DOM directly to apply dynamic styles, leverage angular's **ngClass** and **ngStyle** directives. These directives allow you to donditionally apply CSS classes orstyles based on compnent properties or expressions, reducing the need to manual DOM manipulation.

5. Use **ViewChild** and **ContentChild** sparingly - The **ViewChild** and **ContentChild** decorators provide access to child components or elements in the tmeplate. While these can be useful in certain scenarious, excessive use can lead to tighly coupled componets and increased DOM amnuipulations. Use them sparingly and consider alternative approaches if possible

6. Make use of angular directive and pipes - Angular provides a range of built-in directives and pipes that allow you to manipulate andtransform data directly in the template. utilize these features to reduce the need for manual DOM manipulations

7. Consider using angular renderer2 - if yoiu need to perform low-level DOM manipulation, such as adding or removeing elements dynamically, consider using **Renderer2** instead of directly manipulating the DOM. The renderer 2 provides a save and angular specific way to interact with the DOM while ensuring compatability with server-side rendering and future platform changes.

By following these guidelines, you can minimize diret DOM manipulation in Angular, results in more efficient code, improved perofrmance and better mantainability.

#### Use pure pipes

In angular, pure pipes are powerful features that allow you to transform data in a template without modifying the underlying data source. Pure pipes are designed to be stateless and provide consistent output for a given input. Here are some tips for using pur pipes in angular:

1. Undersntand the purpose of pipes - Pure pipes are ment for transforing data in the template. They should not have side effects or modify the underlying data. Pure pipes reeive input values as arguments and return transformed output values.

2. Use pure pipes for simple transformations - pure pipes are ideal for performing sim9ple dat stransformacion such as formatting dates, converting values, or filtering arrays. The provide a clear and reusable way to apply these transformations in your templates.

3. Avoid complex or resource-intensive operations - pure pipes should not be used for complex or computationally expesnive operations. if The transoformation requires heavy calculations or involves asynchronous operations, its better to handle in teh component class instead of a pure pipe

4. Be cautious with pre pipes and stateful data - pure pipes are stateless, meaning they don't keep track of any interanl state. if youi hav edata that can change frequesntly or depends on external factors, it is better to hanlde the transformation in the cmponent class or cosider uing impure pipes.

5. Understand the perofrmance implications - pure pipes can enahnce performance by memorization results and onl yrecalculate when the inut values changes. However, keeo in mind that using too manu prue pipes in a tmplate with large dataset ca nimpace performance. Test and profile your application to ensure optimal performnace.

6. Avoid pure pipe chaining - chaining multiple pure pipes in a template can lead to unnecessary compulations and performance issues. indead, consider combining the transformation into a single pure pipe or perform the transofrmation in the component class it involves multiple steps.

7. Consider reusability and maintainability - pure pipes are resuable components that na be shared acress multiple template. Design your pure pipes to be generic and flexible so that they can be easily applied in various scenarious, Also, provide clear and meaningful anmes for your pure pipes to improve code maintainability.

Remember, while pure pipes offer convenience and simplicity for data transformation in template, it's important to use the judiciously and consider the performance and maintainability aspects.

#### Avoid heavy compulations in the template

it is generally recommended to avoid heavy compulations in anglar template as it negatively impact performance and user experence. Angular template are primarly intenede for data binding and rendering, not for complex calculations. here are some guidelines to follow:

1. perform heavy computations in the cmponent class. more heavy computations or complex logic from the template to the component class. angular components are better suited for ahndling comultations, and data processing, and business logic. calculate the values in the cmponent and bind the results to the template.

2. Use computed perperties or methods - indead of performancing comoplex computations directly in the templat, expose computed proeprties or method in the cmpoennt class. These properties or methods in the component class. These properties or methods can encapulate the necessary logic and calcualtions, prviding a clean and reusable way to access computed values in the template.

3. Preprocess data before rendering - if you have data that requires heavy processing or transofrmation before displaying it in the template, preprocess the data in the component class. This way, you can store the processed data in a format that is easier and faster t render in the template.

4. Utilize memoization techniques - if youi have compulations that are expensive and are repetitive, cosider using memoization techiques to cache the results. Memoization can help avoid reduentant comopulattion by storing and reusing previously computed values, resulting in improved performance.

5. Leverage observables and async pipes for asynchronous operations - if you sompulations involve asynchronous data operations, such as making API calls or handling asyncrhous data streams, Use angular's observables and async pipes. These mechasisms allo you to handle asynchronous operations in the compoent class and seamlessly update the tempalte with the data becomes available.

6. Optimize and batch compulations - if you must perform comuplations in the tmeplate, optimize them to be as efficient as possible. avoid unnecessary iterations, minimize nested computations, and batch operations when possible. Cosider using angular built in directive like **ngFor**, **ngIf**, and, **ngSwitch** to optimize rendering and reduce the need for manual computations.

7. profile and measure peroformance - regularly profile and measure the proformance of you angular application, particlarly in scenarious involveing heavy computations. Use proser develooer tools or angulars. builtint performanceingprofileing to identify peroframnce bottlenecks and optimize accordingly.

By adhering to these guidelines, youi can keep your angular tempaltes focused on data binding and rendering, which offloading heavy computations to the component class. This approach improves performance, maintainability, and readability of your code.

#### Virtual scrolling (do not use for video)

Virtual scrolling is a techinque used in angular to efficiently render large lists or grids by rendering only a portion of the data that is visible to the user. it help imporve performance and reducdes memory cosumption. Here is an overview of how to implemnt virual scrolling in angualr.

1. Set up the angular material package - angular material provides a **cdk-virtual-scroll-viewport** component that makes implementing virtual scrolling easier. Install angular materia and import the necessary modulesa into the angular app.

2. Prepare your data srouce - create a data source that rpvides the data for virtual scrolling. this can be an array, observable, or custom data source tht implemnts the necessary mehtods (**connect**, **disconnect**, **renderredRangeStream** etc.) The data source should provide the total length. of the data and the portion to be rendered based on the scroll position.

3. implement the virual scrolling compoennt - create a component that uses the **cdk-virtual-scroll-viewport** directive from angular material. Bind the data srouce to the **cdkVirtualFor** directive and configure other properties like **itemSize** or **minBufferPx** as needed.

4. Configure the template - In your compoents template, use the **cdkVirtualFor** dreictive to iterate over the data source and render the individaul items. customize thetemplate to display the desired content for each item.

5. Styling and customization - apply appropriate tyles to the virtual sccrolling component to ensure the desired layout and appearance. You can custimize the appearance of the items and handle events such as click and hover as per your requirements.

6. Handle data updates - if your data source changes dynamically, ensure that you update the data source and trigger a refresh of teh virtual scrolling component accordingly. You might need to call methods like **renderedRangeStream.next()** to refresh the rendered items.

7. test and optimize - test your virtua scrolling implementation with large data sets to ensure smooth performance. if needed, optimize the rendering by adjusting buffer sizes (**minBufferPx** and **maxBufferPx**), turning the item size, and implementating other performance optimization sepcific your use case

Virtual scrolling is a powerful technique that can significantly enhance the performace of angular application with large lists or grids. By rendering only the visible portion of the data, virutal scrolling reduces rendering time and memory cosumption, resulting in a smother user expereince.

#### Template structure directives

Template structural directives in angular are directives that allo you to conditionally add or remove elements from the DOM based on certain conditions. They provide a way to dynamically modify the structure of teh tmepplate. angular provides three build-in structural directive **ngIf**, **ngFor** and **ngSwitch**.

1. ngIf - The **ngIf** directive conditionally renders or removes elmeents from the DOM based on a given expression. it evaluates the epxression