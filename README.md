# `jbrowse-plugin-biothings`

> Adapts to APIs like mygene.info to get super rich gene annotations

## Install

### For use in [JBrowse Web](https://jbrowse.org/jb2/docs/quickstart_web)

No installation required

### For use in [`@jbrowse/react-linear-view`](https://www.npmjs.com/package/@jbrowse/react-linear-genome-view)

```
yarn add @gmod/jbrowse-plugin-biothings
```

## Usage

### In [JBrowse Web](https://jbrowse.org/jb2/docs/quickstart_web)

#### Development

```
git clone https://github.com/cmdcolin/jbrowse-plugin-biothings-api.git
cd jbrowse-plugin-biothings-api
yarn
yarn start
```

Then open JBrowse Web to (assuming it is running on port 3000):

http://localhost:3000/?config=http://localhost:9000/jbrowse_config_biothings.json

#### Production

Add to the "plugins" of your JBrowse Web config:

```json
{
  "plugins": [
    {
      "name": "Biothings",
      "url": "https://ghcdn.rawgit.org/cmdcolin/jbrowse-plugin-biothings-api/master/rawgit/jbrowse-plugin-biothings.umd.production.min.js"
    }
  ]
}
```

### In [`@jbrowse/react-linear-view`](https://www.npmjs.com/package/@jbrowse/react-linear-genome-view)

```tsx
import React from 'react'
import 'fontsource-roboto'
import {
  createViewState,
  createJBrowseTheme,
  JBrowseLinearGenomeView,
  ThemeProvider,
} from '@jbrowse/react-linear-view'
import Biothings from 'jbrowse-plugin-biothings'

const theme = createJBrowseTheme()

function View() {
  const state = createViewState({
    assembly: {
      /* assembly */
    },
    tracks: [
      /* tracks */
    ],
    plugins: [Biothings],
  })
  return (
    <ThemeProvider theme={theme}>
      <JBrowseLinearGenomeView viewState={state} />
    </ThemeProvider>
  )
}
```

## Screenshot

![](img/1.png)
