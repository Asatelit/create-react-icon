This tool generates SvgIcon components for a set of svg icons, forked from @material-ui/icons.

## Running the build

The build the icons.

```sh
yarn install
yarn build
```

## Generated folders

The build generates the appropriate `.js` files in the `build` folder.

## Advanced usage and Custom builds

`node build.js --help` can be used to display the options available for building.

You can build your own SVG icons as well as collections through command line options.

* `--output-dir` - Directory to output generated components.
* `--svg-dir` - Directory containing the source SVG icons.
* `--inner-path` - "Reach into" subdirs, since libraries like material-design-icons
  use arbitrary build directories to organize icons, e.g. "action/svg/production/".
* `--file-suffix` - Process only files ending with the specified suffix/
* `--rename-filter`  - Apply a custom filter to rename the generated icons.
  The default and Material Design filters can be found in `filters/rename`.

## Usage

When importing an icon, keep in mind that the names of the icons are `PascalCase`, for instance:
- [`delete`](https://material.io/tools/icons/?icon=delete&style=baseline) is exposed as `@material-ui/icons/Delete`
- [`delete forever`](https://material.io/tools/icons/?icon=delete_forever&style=baseline) is exposed as `@material-ui/icons/DeleteForever`

## Imports

- If your environment doesn't support tree-shaking, the **recommended** way to import the icons is the following:
```jsx
import AccessAlarmIcon from './icons/AccessAlarm';
import WarningIcon from './icons/Warning';
```

- If your environment support tree-shaking you can also import the icons this way:
```jsx
import { AccessAlarm, Warning } from './icons';
```

Note: Importing named exports in this way will result in the code for *every icon* being included in your project,
so is not recommended unless you configure [tree-shaking](https://webpack.js.org/guides/tree-shaking/). It may also impact Hot Module Reload performance.

