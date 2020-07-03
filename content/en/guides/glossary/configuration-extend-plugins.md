---
title: "API: The extendPlugins Property"
description: The extendPlugins property lets you customize Nuxt.js plugins.
menu: extendPlugins
category: Glossary
categoryPosition: 4
---

> The extendPlugins property lets you customize Nuxt.js plugins ([options.plugins](/api/configuration-plugins)).

- Type: `Function`
- Default: `undefined`

You may want to extend plugins or change plugins order created by Nuxt.js.
This function accepts an array of [plugin](/api/configuration-plugins) objects and should return array of plugin objects.

Example of changing plugins order (`nuxt.config.js`):

```js
export default {
  extendPlugins (plugins) {
    const pluginIndex = plugins.findIndex(
      ({ src }) => src === '~/plugins/shouldBeFirst.js'
    )
    const shouldBeFirstPlugin = plugins[pluginIndex]

    plugins.splice(pluginIndex, 1)
    plugins.unshift(shouldBeFirstPlugin)

    return plugins
  }
}
```