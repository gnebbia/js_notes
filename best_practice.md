- use const by default and switch to let only when needed;
- never use var;
- use camelCase;
- always `'use strict';` to force variable definition;
- when using global variables be sure to use an `app` object as a container
  object to not pollute the namespace, such as:
```javascript
app = {
    configFile: "path/to/config.yml",
    globVar1: "myValue",
    globVar2: 33
}
```

