# enforce valid `v-html` directives (valid-v-html)

- :white_check_mark: The `"extends": "plugin:vue/recommended"` property in a configuration file enables this rule.

This rule checks whether every `v-html` directive is valid.

## :book: Rule Details

This rule reports `v-html` directives in the following cases:

- The directive has that argument. E.g. `<div v-html:aaa></div>`
- The directive has that modifier. E.g. `<div v-html.bbb></div>`
- The directive does not have that attribute value. E.g. `<div v-html></div>`

This rule does not check syntax errors in directives because it's checked by [no-parsing-error] rule.

:-1: Examples of **incorrect** code for this rule:

```html
<template>
    <div>
        <div v-html></div>
        <div v-html:aaa="foo"></div>
        <div v-html.bbb="foo"></div>
    </div>
</template>
```

:+1: Examples of **correct** code for this rule:

```html
<template>
    <div>
        <div v-html="foo"></div>
    </div>
</template>
```

## :wrench: Options

Nothing.

## :couple: Related rules

- [no-parsing-error]


[no-parsing-error]: no-parsing-error.md
