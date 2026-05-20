# CSS & HTML Notes

## Block, Inline & Inline-Block Elements

### Block Elements
- Take the entire line width by default.
- Even if width is reduced, they still start on a new line.

Examples:
```html
<p></p>
<div></div>
```

---

### Inline Elements
- Behave like text.
- Stay within the same line.
- Width/height usually don't work properly.

Examples:
```html
<strong></strong>
<u></u>
<span></span>
```

---

### Inline-Block Elements
- Take only the space they need.
- Can stay on the same line.
- Width and height work properly.

Examples:
```html
<img>
```

---

### `display` Property
Used to change element behavior.

```css
display: block;
display: inline;
display: inline-block;
display: flex;
display: grid;
```

---

# Divs & Containers

## `div`
- A generic container/box.
- By default:

```css
display: block;
width: 100%;
```

---

## Why Use Containers?
Suppose we have:
- video title
- channel name
- video stats

We want:
- them stacked vertically
- but the whole section should not take the entire page width

So we wrap them inside a container.

```html
<div class="video-info">
  <p>Title</p>
  <p>Channel</p>
  <p>Stats</p>
</div>
```

Then:

```css
.video-info {
  display: inline-block;
}
```

Now the container only takes required space.

---

# Images

## Problem
Images keep their original size and may overflow containers.

## Solution

```css
img {
  width: 100%;
}
```

Now the image fits the container width.

---

## `object-fit`

### `contain`
Entire image visible inside container.

```css
object-fit: contain;
```

### `cover`
Container fully filled by image.

```css
object-fit: cover;
```

---

# Grid vs Inline-Block

## Inline-Block
- Works
- But alignment becomes messy

## Grid
- Better alignment
- Cleaner layouts

---

# Flexbox

## Basic Setup

```css
.container {
  display: flex;
  flex-direction: row;
}
```

---

## Important Properties

### `flex: 1`
Equivalent to:

```css
1fr
```

in Grid.

---

### `justify-content`
Controls horizontal spacing.

```css
justify-content: center;
justify-content: start;
justify-content: space-between;
```

---

### `align-items`
Controls vertical alignment.

```css
align-items: center;
align-items: start;
align-items: end;
align-items: stretch; /* default */
```

---

### `flex-shrink: 0`
Prevents shrinking.

```css
flex-shrink: 0;
```

---

# Useful CSS Properties

## Negative Margin

```css
margin-left: -1px;
```

---

## Box Shadow

```css
box-shadow: inset 1px 2px 3px rgba(0,0,0,0.05);
```

Format:

```css
box-shadow: inset x y blur color;
```

---

## `width: 0`
Useful in flex layouts when an input has a default minimum width.

```css
width: 0;
```

Allows shrinking properly.

---

## `overflow: hidden`
Hides overflowing content.

Useful for:
- rounded corners
- clipping content

```css
overflow: hidden;
```

---

# CSS Positioning

Whenever an element appears on top of another element, positioning is involved.

---

## `position: static`
Default behavior.

```css
position: static;
```

---

## `position: fixed`

- Removed from normal page flow
- Floats above page
- Stays fixed during scrolling

```css
position: fixed;
top: 20px;
left: 0;
```

---

## Important Notes

If both `left` and `right` are used:

```css
left: 0;
right: 0;
```

the element stretches to satisfy both.

---

## Header Problem
Fixed elements cover page content.

Solution:

```css
body {
  padding-top: 60px;
}
```

---

## `position: absolute`

Similar to fixed, but positioned relative to the page.

```css
position: absolute;
```

---

## Difference

### Fixed
- Relative to browser window
- Doesn't move while scrolling

### Absolute
- Relative to page
- Moves while scrolling

---

## `position: relative`

Behaves normally unless absolute elements are placed inside it.

```css
position: relative;
```

Then:

```css
.child {
  position: absolute;
}
```

Now the child becomes relative to the parent instead of the page.

---

## YouTube Thumbnail Duration Example

We want:
- duration fixed on thumbnail
- but thumbnail itself should scroll

Solution:

```css
.thumbnail {
  position: relative;
}

.duration {
  position: absolute;
}
```

---

# Positioning Rule

If positioned elements overlap:
- the element written later appears on top.

To fix:

```css
z-index: 1;
```

Higher `z-index` appears above lower ones.

---

# Tooltips

## Basic Idea
Hide initially:

```css
opacity: 0;
```

Show on hover.

---

## Useful Properties

### Disable interactions

```css
pointer-events: none;
```

---

### Animation timing

```css
transition: opacity 0.15s;
```

---

### Prevent text wrapping

```css
white-space: nowrap;
```

---

# Example CSS

```css
.thumbnail{
    width: 300px;
    height: 300px;

    object-fit: contain;
    object-position: bottom;

    border-width: 2px;
    border-color: red;
    border-style: solid;
}
```

---

```css
.search-bar{
  font-size: 33px;
  margin-left: 34px;
}
```

---

```css
.channel-picture {
  display: inline-block;
  vertical-align: top;
  width: 50px;
}

.video-info {
  display: inline-block;
  vertical-align: top;
  width: 200px;
}
```