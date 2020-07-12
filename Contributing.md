Here are the official contributing guidelines! The following sections are included:

* [Frontend](#frontend)
  * [Code Overview](#code-overview) (WIP)
  * [General rules](#general-rules)
  * [Translations](#translations)
* [Backend](#backend) (WIP)
  * [Code Overview](#code-overview-1) (WIP)
  * [General rules](#general-rules-1) (WIP)

# Frontend
## Code Overview
This section is WIP.

## General rules

Variables are generally named using [snake case](https://en.wikipedia.org/wiki/Snake_case), which in short is just undercase with words separated by an underscore
* Example: `let this_is_a_variable = true`
* Don't specify the type unless the variable is set to null by default
  * Example: `let this_is_a_variable: boolean = null`

The frontend is split up into various components, so if you are ever adding functionality that could logically fit into a separate component, please do so. Add new components to the `src/app/components` directory, or if the component is exclusively a dialog, place it in the `src/app/dialogs` directory.

All API calls should be done through `posts.services.ts`, also called PostsService. This service also keeps track of the config and current user info.

## Translations

If you add any strings to the frontend that will appear in the UI, make sure to make it translatable. How you do so depends on where the string exists (purely in HTML or in TypeScript), these next two subsections will explain how to do so.

Once you are done adding translations, run `ng xi18n --output-path assets/i18n` from the root directory to re-generate the needed XLIFF source file. This will be called `messages.xlf`, but rename it to `messages.en.xlf` to indicate that it is the new English source file.

### HTML strings

Let's say you have the following HTML element:

```
<span>This is a string I want to translate.</span>
```

To make it translatable, surround the string with an `<ng-container>` element like so:

```
<span><ng-container i18n="String description">This is a string I want to translate.</ng-container></span>
```

That's all!

### TypeScript strings

To properly translate strings that are defined in TypeScript, the [Select ICU](https://angular.io/guide/i18n#translate-alternate-expressions) must be used in the corresponding HTML. You can see where we do this in [settings.component.html](https://github.com/Tzahi12345/YoutubeDL-Material/blob/9cf4949c304e2559c1ae9fad557f93bf1d572adc/src/app/settings/settings.component.html)

```
<span i18n="Settings cancel and close button">{settingsAreTheSame + "", select, true {Close} false {Cancel}}</span>`
```

The brackets are the important part here, encasing an "if statement" for the translatable strings.

If the settings have changed, the button will have the "Cancel" label, but if they haven't changed, it'll just say "Close". The `+ ""` after `settingsAreTheSame` is just to convert the boolean variable into a string, since the ICU select comparisons are string to string.

# Backend (WIP)
## Code Overview (WIP)
This section is WIP.
## General rules (WIP)
This section is WIP.
