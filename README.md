# be-deobjectified

Vague mission statement

In the progressive web application era, HTML is a much better format for sending the end user information.  Unfortunately, 99% of API's don't provide an HTML (or even XML) output format.  

[o2h-cw](https://github.com/bahrus/o2h-cw) is a cloudflare worker that provides a way to turn any public-facing API into an API that provides HTML.  The shape of the HTML can be configured via a declarative JSON configuration.

But this solution doesn't work in an intranet setting, where the api can't be exposed as a cloudflare worker.  And some scenarios need to be more local to the browser.

So be-deobjective provides a way to do the same thing in a browser worker thread (like a service worker).  Hopefully.  Worst case, it runs the conversion in the main thread, using the same o2h library.

Verbose:

```html
<template be-deobjectified='{
    "obj": {
        
    },
}'>
    <!-- wrapperOpen -->
    <form>
    <!-- /wrapperOpen -->
        <!-- objectPropOpen -->
        <details>
            <summary>$0</summary>
        <!-- /objectPropOpen -->
        <!-- objectPropClose -->
        </details>
        <!-- /objectPropClose -->
    <!-- wrapperClose -->
    </form>
    <!-- /wrapperClose -->
    <!-- pathOverrides -->
    <template path=...>
    </template>
    <!-- /pathOverrides -->
</template>
```

Succinct:

```html
<template be-deobjectified="https://example.com/api/myapi?id=123">
    <form o2h-wrapper>
        <details o2h-object-prop>
            <summary>$0</summary>
        </details>
    </form>
    <template o2h-path-overrides path=...>
    </template>
</template>
```
