# Angular Common Syntax

There's a lot of different kinds of syntax you'll see in Angular, here's a few examples of the most common ones.

## Two Curly Braces

The syntax `{{ variableName }}` means that this will be replaced with the actual value of that variable in the browser. For example, if you put `{{ title }}` in the HTML, that will display whatever value you have the property `this.title` set to in the component's `.ts` file.

This can also be used for displaying any JavaScript expression, so `<span>{{ 2 * 2 }}</span>` would display as `<span>4</span>` in the browser.

You can consider `{{ variable }}` as a new way of how you would write ` `${variable}` ` in plain JavaScript.

## Square Brackets

Using `[prop]="variableName"` means you are binding the HTML property in the square brackets to be equal to the value of the variable name in the quotes. The variable comes from the component property in your `.ts` file.

For example:

```
   <div [hidden]="hideElement"></div>
```

means that hidden will be set to true on this div if `this.hideElement` is set to true on the component class.

## Parenthesis

Using `(<eventName>)="functionName"` means you are binding an event, such as a click, to a method in the component class.

For example:

```
    <button (click)="toggleHidden()"> Show / Hide </button>
```

will call `this.toggleHidden()` on the component class.

## Parenthesis and Square Brackets combined

Using `[(variableName)]="otherVariableName"` is used for two-way binding, meaning that if one variable is changed, then the other is also changed.

This is most commonly used for input fields with ngModel, where

```
<input [(ngModel)]="appInput" />
<p>{{ appInput }}</p>
```

means that if I type something in the input, the value of `appInput` will be changed to whatever I type in.
