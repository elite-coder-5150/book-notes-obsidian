Tags: #solid-primciple

The SOLID principle are a set of guidelines for writing maintainable and scalable software using oop

#### Single responsibility Principle (SRP) 

A class should hve only one reason to change. theis pronciple suggests that a class should have only one responsiblity or task to perform, and if it has more than one responsiblity, it should be broken down into smaller, more focused classes.

```typescript
class Customer {
  private name: string;
  private email: string;
  private phone: string;

  constructor(name: string, email: string, phone: string) {
    this.name = name;
    this.email = email;
    this.phone = phone;
  }

  getName(): string {
    return this.name;
  }

  getEmail(): string {
    return this.email;
  }

  getPhone(): string {
    return this.phone;
  }
}

class CustomerRepository {
  private customers: Customer[] = [];

  addCustomer(customer: Customer): void {
    this.customers.push(customer);
  }

  getCustomers(): Customer[] {
    return this.customers;
  }
}
```

In the code above, the Customer class is responsible for holding customer data, including name, email, and phone number. it has mehtod for getting each of these attributes.

The CustomerRepository class is responsible for storing and retrieving customer data. it has methods for adding a new customer to the database and getting all the customers from the database.

By spearating the concerns of storing and retrieving customer data from the customer calss and putting them into separate CustomerRepository class, we are adjering to the SRP. The customer class has a single responsibliity, which is to hold customer data, while the customer respsitory class has a single responsibility, which is to manage custom data storage and retrieval.

The approach has several benefits, including making the code more modular, easier to maintain and more testable. It also allows for greater flexibility, as changes to one class will not affect the other classes as long as the interface between the calsses remains the same.

#### Open-Closed Principle (OCP)

2. A class should be open for extension but closed to modification. this suffests that a class should be desinged in such a way that new functionality can be added without modifying its existing code. this typically acheives throught the user of interfaces, abstract classes, and inheritance.

```typescript
abstract class Shape {
  abstract area(): number;
}

class Circle extends Shape {
  constructor(private readonly radius: number) {
    super();
  }

  area(): number {
    return Math.PI * this.radius ** 2;
  }
}

class Rectangle extends Shape {
  constructor(private readonly width: number, private readonly height: number) {
    super();
  }

  area(): number {
    return this.width * this.height;
  }
}

class AreaCalculator {
  constructor(private readonly shapes: Shape[]) {}

  calculate(): number {
    let totalArea = 0;
    for (const shape of this.shapes) {
      totalArea += shape.area();
    }
    return totalArea;
  }
}
```

In the code above, the **shape** class is declared as an abstract class with an abstract method **area**. The **circle** and **rectangle** classes extend the **shape*** class and provide their own implementations of the **area** method.

The **AreaCalculator** class is responsible for calculating the total area of the list of shpaes, which it receives as an array of **Shape** objects. The **AreaCalculator** class does not need to know the specific type of shapes it is calculating the area for, only that they all implement the **area** method. this means that the AreaCalculator class is open for extension, in that it can handlenew types of shpaes that implement the shape interface, but closed to modification, in that it does not need to be modified to accommodate new shapes.

Using the OCP in the way allows for more flexible and maintainable code, as new shapes can be added to the sustem without requiring changes to the existing code. Instead, new shape are simply implemented the shape interface and be passed to the AreaCalculator class for area calculations.

#### Liskov Substitution principle (LSP)

A sub class should be able to substitute for its superclass or parent class. This principle suggest that the object of the parent class should be replaceable with objects of a subclass without affecting the correctlness of the program. This requires that the subclass conforms to the same interface and behavioral contract as the parent class.

```typescript

class rectangle {
	constructor(private width: number, private height: number) {}

	getWidth(): void {
		return this.width;
	}

	getHeight(): void {
		return this.height
	}

	setHeight(height: number): void {
		this.height = height;
	}

	setWidth(width: number): void {
		this.width = width;
	}

	getArea(): number {
		return this.width * this.height
	}
}
class square extends rectangle {
	setWidth(width: number) : void {
		this.width = width;
		this.height = width;
	}

	setHeight(height: number) : void {
		this.width = height;
		this.height = height;
	}
}
```

In the code above, the rectangle class has a getWidth(), getHeight(), setHeight(), and setWidth(), and a getArea() method. The square class is a subclass of rectangle.I simply overrides the setWidth and setHeight methods.

These two classes adheres to the Liskov Substution principle because objects of the square class can be substituted for objects of the rectangle class wiout affecting the correctness of the program. Since the square class extends the rectangleclass and implements all of its methods, it can be used in the same way as a rectangle object, and will produce the expecte results.

In other words, the square class is a subtype of the rectangle class, and conforms to the same interface and behaviroal constract as the rectangle clas. this allows for greater flexibility and modularity in the code, as objects the square class an be used in any situation where a rectangle object is expected.

#### interface segregation principle

Is one of the solid principles of ood. the isp states that clients should not be forced to depind on interfaces they do not use. In other words, interfaces should