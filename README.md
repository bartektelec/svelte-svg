<div align="center">

# 🖍️svelte-svg-transform

[Live Demo](https://bartektelec.github.io/svelte-svg-transform/)

A tiny library that makes it easier for you to add SVGs and tranform them in your svelte project.
You won't need to rename your `.svg` files to `.svelte` and manually edit them.
Independent from DOMParser, so it works just fine during server-side rendering.

[![release version](https://img.shields.io/npm/v/svelte-svg-transform)](https://www.npmjs.com/package/svelte-svg-transform) [![weekly download count](https://img.shields.io/npm/dm/svelte-svg-transform)](https://npmcharts.com/compare/svelte-svg-transform?interval=30&minimal=true) ![primary language procentage](https://img.shields.io/github/languages/top/bartektelec/svelte-svg-transform) ![workflow build status](https://img.shields.io/github/actions/workflow/status/bartektelec/svelte-svg-transform/npm-publish.yml) ![last commit badge](https://img.shields.io/github/last-commit/bartektelec/svelte-svg-transform) [![licence badge](https://img.shields.io/npm/l/svelte-svg-transform)](https://github.com/bartektelec/svelte-svg-transform/blob/main/LICENSE)

</div>
<hr />

## Install

```sh
npm install svelte-svg-transform
```

## Usage

- Import in your component and pass it your SVG
- Import your Icon's raw markup
- Pass the icon to the component and transform it using props

```tsx
// important! include the ?raw at the end of your SVG import
import MyIcon from '../path/to/icon.svg?raw';
// component is default exported so you can call it whatever you want!
import SvgTransform from 'svelte-svg-transform';

<span class="text-red-500">
	<SvgTransform
		svg={MyIcon}
		width={32}
		strokeWidth={3}
		stroke="currentColor"
	/>
</span>;
// => outputs a 32px x 32px INLINE svg
// => with 3px thick stroke of same color as parent's text
```

## Props

The component exposes some props that make it easier to manipulate SVG type files.
Make sure to pass your SVG's **raw** markup to the component like so:

```tsx
import SvgIcon from 'svelte-svg-transform';
import MyIcon from '../path/to/icon.svg?raw';

<SvgIcon svg={MyIcon} />;
```

From there you can use these props on the component:

### svg

Type: `string (svg markup)`
Required

Accepts only raw svg markup that you want to transform.

### width

Type: `number`
Default: 20

Sets svg's width to desired pixels.

### height

Type: `number`
Default: Same as width

Sets svg's height to desired pixels, if not passed will use the same as width.

### fill

Type: `string`

Override any hard-coded fill colors _except none_

### stroke

Type: `string`

Override any hard-coded stroke colors _except none_

#### fillOpacity

Type: `number`
Range: 0-1
Optional

Change svg's internal fill-opacity properties (except none) to any value you want.

#### strokeWidth

Type: `number`
Optional

Change svg's internal stroke-width properties (except none) to any value you want.

#### strokeLineCap

Type: `string`
Optional

Change svg's internal stroke-line-cap properties (except none) to any value you want.

#### strokeOpacity

Type: `number`
Range: 0-1
Optional

Change svg's internal stroke-opacity properties (except none) to any value you want.

## Licence

[MIT](https://opensource.org/licenses/MIT)
