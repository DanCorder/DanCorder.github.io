---
layout: til
title: "Svelte Warning Codes"
---

Having just spent close to an hour trying to find the right way to suppress this Svelte warning

`(!) Plugin svelte: A11y: Avoid using autofocus`

I wanted to record how to do it for future reference.

The easyish part is using `<!-- svelte-ignore error-code -->` the harder part is working out what `error-code` should actually be.

Update: The headings here seem to match the error codes: <https://svelte.dev/docs#accessibility-warnings>

~~I couldn't find a nice list documented anywhere, so failing that here's the relevant source file:~~

~~<https://github.com/sveltejs/svelte/blob/master/src/compiler/compile/compiler_warnings.ts>~~