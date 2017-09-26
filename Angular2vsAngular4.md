# Angular 4 vs Angular 2 Cheat-Sheet

* ## Better ngIf...

Angular 2:
``` HTML
    <div *ngIf="condition"></div>
    <div *ngIf="!condition"></div>
```
Angular 4:
```HTML
    <div *ngIf="condition; else conditionNotTrue"></div>

    <ng-template #conditionNotTrue> </ng-template>
    <!-- Note it uses ng-template on Angular  4-->
```

* ## ...and Better ngFor 
Angular 2:
``` HTML
    <ul>
        <li *ngFor="let item of list, let i = index">
            {{ item.name }}
        </li>
    </ul>
```
Angular 4:
```HTML
    <ul>
        <li *ngFor="let item of Observable | async as list, index as i">
        <!-- now you can apply the observable return to a alias inside the ngFor-->
            {{ item.name }}
        </li>
    </ul>
```
* ## Renderer vs Renderer 2 
Angular 2:

[Renderer](https://angular.io/api/core/Renderer)

Angular 4:

[Renderer 2](https://angular.io/api/core/Renderer2)

* ## Better validation
Angular 2:
``` HTML
    <input  type="mail"
            name="mail"
            [(ngModel)]="user.mail"
            required
            pattern="(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])"
            placholder="mail@angular2.com">
    
```
Angular 4:
```HTML
    <input  type="mail"
            name="mail"
            [(ngModel)]="user.mail"
            required
            email
            placholder="mail@angular4.com">
```
* ### You may also give a look at the latest news in typescript since new angular versions should also use new TS versions
 - https://github.com/Microsoft/TypeScript/wiki/What's-new-in-TypeScript
 