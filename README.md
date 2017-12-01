# double-underscore-media-queries
(i know, it's long names! can't find a good one :neutral_face:)
is the most readable syntax and manageable media queries in your sass code!

## Installation
download the sass files [here](https://raw.githubusercontent.com/arisunarya/double-underscore-media-queries/master/_double-underscore-media-queries.scss), and import in your main sass files `@import 'path/to/double-underscore-media-queries';`

## Example of Usage
``` scss
// target xs only
@include __(xs) {
  line-height: 20px;
}
// target from sm to down
@include __(sm up) {
  font-size: 18px;
}
// target from md up to infinite
@include __(md down) {
  font-size: 18px;
}
// target from md to xl only
@include __(md to xl) {
  font-size: 24px;
}
// target from xxl up to infinite
@include __(xxl) {
  font-size: 24px;
}
```
**Default breakpoints setup :**

| Name | Width |                            |
|------|-------|----------------------------|
| xs   | 0px   | Extra small devices        |
| sm   | 576px | Small devices              |
| md   | 768px | Medium devices             |
| lg   | 992px | Large devices              |
| xl   | 1200px| Extra large devices        |
| xxl  | 1440px| Double extra large devices |

## Configurations
you need to overide `$__media-queries` to setup your breakpoint names and their widths.
``` scss
// overides default breakpoints
$__media-queries: (
  phone: 0,
  big-phone: 576px,
  tablet: 768px,
  big-tablet: 992px,
  desktop: 1200px,
  big-desktop: 1440px
);

// and use it like this!
.myHeading {
  @include __(tablet to desktop) {
    font-size: 16px;
    line-height: 1.25;
 }
}
// how cool is that?
```
**Notes & Requirements :**
- you must set correct breakpoint order, meaning width value need to be higher than previous breakpoint.
- first breakpoint names must be set to `0`.
- if you have less than 5 breakpoints, the `'to'` keywords will not going to work, because it's useless, use keywords `'up'` and `'down'` instead.
- the smallest breakpoint can't use `'up'` keywords
- the biggest breakpoint can't use `'down'` keywords
- assuming `'xs'` is smallest and `'xxl'` largest breakpoints, of course you can't use `'xs to xxl'` keywords, that's just hilarious! :joy:


## That's it, what's next?
- better documentations.
- for now it's just support `px` unit, in the future, maybe it's will support  `em` or `rem` units.
- responsive utillities are coming, functionality such as hide and show elements in certain breakpoints.

**Help, ideas and suggestions are welcome :)**

