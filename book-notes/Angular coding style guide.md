#### File structure conversion

Some code examples display a file that has one or more similarly named companion files.

The guideline uses the shortcut **hero.component.ts|html|scss|spec** to represent those various files. Using this shortcut makes the guide's file structure easier to read and more tarse.

#### Single responsibility

Apply the single responsibility principle to all components, services and other symbols. This helps make the application cleaner, easier to read and maintain, and as a result make it much easier to test the components

##### Rule of One

do define one thing, such as a service or component, per file.
consider limiting files to 400 lines of code.

#### Why?

One component per file makes it far easier to read, maintain, and avoid collisions with teams in source control. And it avoid hidden bug that often arise when combining component in a file where they amay share variables, create unwanted closures, or unwanted coupling with dependencies.

Besides, a single component can be the default export for its file which facilitates lazy loading with the router.

The key is to make code more reusable, easier to read, and less mistake prone.

The following is a negative example that defines the appComponent, bootstraps the app defined the hero model object, and loads heros fro the server all in the same file. don't do this.

```typescript
/* avoid */
import { Component, NgModule, OnInit } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

interface Hero {
  id: number;
  name: string;
}

@Component({
  selector: 'app-root',
  template: `
      <h1>{{title}}</h1>
      <pre>{{heroes | json}}</pre>
    `,
  styleUrls: ['app/app.component.css']
})
class AppComponent implements OnInit {
  title = 'Tour of Heroes';

  heroes: Hero[] = [];

  ngOnInit() {
    getHeroes().then(heroes => (this.heroes = heroes));
  }
}

@NgModule({
  imports: [BrowserModule],
  declarations: [AppComponent],
  exports: [AppComponent],
  bootstrap: [AppComponent]
})
export class AppModule {}

platformBrowserDynamic().bootstrapModule(AppModule);

const HEROES: Hero[] = [
  { id: 1, name: 'Bombasto' },
  { id: 2, name: 'Tornado' },
  { id: 3, name: 'Magneta' }
];

function getHeroes(): Promise<Hero[]> {
  return Promise.resolve(HEROES); // TODO: get hero data from the server;
}
```

A better solution is to divide each section into its own file.

After doing just a little research and I have discovered if you components exceeds 400 lines of code
