# `smithy-types-override`

[![NPM Version](https://img.shields.io/npm/v/smithy-types-override?color=blue)](https://npmjs.com/package/smithy-types-override)

If you have multiple versions of `@smithy/types` in your dependencies, it may break type checking.

To fix type checking:

1. Install this package

```bash
npm install --save-dev smithy-types-override
```

2. Update your `package.json` to use package overrides

```json
{
  "overrides": {
    "dependency": {
      "smithy-types-override": "$@smithy/types"
    }
  }
}
```

3. Update your imports to use the overridden file

```ts
import type { NodeJsClient, BrowserClient } from "smithy-types-override";
```

4. ???

5. Profit

Your types will now always be imported from the latest version of `@smithy/types` and you can avoid type errors 🎉

The permanent solution would be for all of your dependencies to use the same and latest version of `@smithy/types`, which may never happen.
