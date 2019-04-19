# Angular Animated List

* App using interpolation, property-binding, event-binding and Formbuilding to add text itmes to a list.

*** Note: to open web links in a new window use: _ctrl+click on link_**

## Table of contents

* [General info](#general-info)
* [Screenshots](#screenshots)
* [Technologies](#technologies)
* [Setup](#setup)
* [Features](#features)
* [Status](#status)
* [Inspiration](#inspiration)
* [Contact](#contact)

## General info

* Routing module allows user to navigate between Home and About pages.

* Item is added to an existing list of Programming Items.

* Angular FormBuilder used to create a simple form.

## Screenshots

![Example screenshot](./img/list-items.png).

## Technologies

* [Angular v7.2.13](https://angular.io/) & [Angular CLI v7.3.8](https://cli.angular.io/).

* [RxJS Library v6.4.0](https://angular.io/guide/rx-library) used to [subscribe](http://reactivex.io/documentation/operators/subscribe.html) to the API data [observable](http://reactivex.io/documentation/observable.html).

* [Angular Forms Module](https://angular.io/api/forms) used for form entry.

## Setup

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code Examples

* Home.Component class from `home.component.ts`

```typescript
export class HomeComponent implements OnInit {

  itemCount: number;
  btnText: string = 'Add an item to the list';
  goalText: string = 'Another programming item';
  goals = [];

  constructor(private _data: DataService) { }

  ngOnInit() {
    this._data.goal.subscribe(res => this.goals = res);
    this.itemCount = this.goals.length;
    this._data.changeGoal(this.goals);
  }

  addItem() {
    this.goals.push(this.goalText);
    this.goalText = '';
    this.itemCount = this.goals.length;
    this._data.changeGoal(this.goals);
  }

  removeItem(i) {
    this.goals.splice(i, 1);
    this._data.changeGoal(this.goals);
  }
}
```

## Features

* Angular animations library used to make data entry more interesting.

* Updated to latest Angular 7 version.

## Status & To-Do List

* Status: Simple working app that adds form data to a list.

* To-Do: add functionality, including form validation.

## Inspiration

* [Gary Simon of Coursetro Tutorial: Learn Angular 5 in less than 60 Minutes - Free Beginner's Course](https://www.youtube.com/watch?v=oa9cnWTpqP8&t=50s)

## Contact

Created by [ABateman](https://www.andrewbateman.org) - feel free to contact me!
