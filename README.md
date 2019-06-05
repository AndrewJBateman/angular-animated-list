# Angular Animated List

* App using services, routing, interpolation, property & event-binding and Formbuilding to add text items to a list.

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

* RxJS BehaviousSubject used: A Subject that requires an initial value and emits its current value to new subscribers

## Screenshots

![Example screenshot](./img/list-items.png).

## Technologies

* [Angular v8.0.0](https://angular.io/)

* [Angular CLI v8.0.1](https://cli.angular.io/).

* [RxJS Library v6.5.2](https://angular.io/guide/rx-library) used to [subscribe](http://reactivex.io/documentation/operators/subscribe.html) to input data [observable](http://reactivex.io/documentation/observable.html).

* [Angular Forms Module](https://angular.io/api/forms) used for form entry.

## Setup

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

Run `ng build --prod` to create an optimzed build file.

Run `ng build --prod --base-href="https://YOURUSERNAME.github.io/REPO-NAME/"` to create an optimised build file and deploy to your Github repo.

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

* Updated to latest Angular 8 version - all dependency issues corrected.

## Status & To-Do List

* Status: Simple updated and working app that adds form data to a list.

* To-Do: add functionality, including form validation.

## Inspiration

* [Gary Simon of Coursetro Tutorial: Learn Angular 5 in less than 60 Minutes - Free Beginner's Course](https://www.youtube.com/watch?v=oa9cnWTpqP8&t=50s)
* [written version of Coursetro Tutorial: Learn Angular 5 from Scratch - Angular 5 Tutorial](https://coursetro.com/courses/19/Learn-Angular-5-from-Scratch---Angular-5-Tutorial)

## Contact

Repo created by [ABateman](https://www.andrewbateman.org) - feel free to contact me!
