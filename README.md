# be-deobjectified

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
