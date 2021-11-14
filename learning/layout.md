# 1)Float
1. Element is remove from the normal flow.
2. then container will not adjust its height to the element.
3. float:left and float:height.

```css
.container{width:1200px;}
.article{
     /* remaining 75px will be margin  */
     width:825px;
     float:left;
}

.aside{ width:300px; float:right;}
.footer{ clear:both}

h1 {
  float: left;
}
nav {
  float: right;
}

.main-header::after {
  clear: both;
  content: '';
  display: block;
  /* main-header child h1 and h2 will remove from place so there will be no height(only padding) doing this will give height */
}

.clearfix::after {
  clear: both;
  content: '';
  display: block;
}
```

# 2)Flexbox
1. set of css properties for building 1-d layout
2. main idea is that empty space in container element can be automatically divided by its child elements
3.Flex container(display:flex), flex items. main axis and cross axis.

```css
.container{
  display:flex;
  /* set gap to 30px to each items not include last item in container */
  gap:30px;
}

.el{
  flex-grow:0;
  flex-shrink:1;
  flex-basis:auto;

  flex-basis:200px;
  flex-shrink:0;
  flex-grow:1;
}

.el--1{
  flex-grow:1;
}
 .row {
  display: flex;
  align-items: flex-start; /* make second items not stratch to end */
  gap: 75px;
  margin-bottom: 60px;
}

article {
  flex: 1;/* Take space required for it */
  margin-bottom: 0;
}

aside {
  DEFAULTS:
  flex-grow: 0;
  flex-shrink: 1;
  flex-basis: auto;
  flex: 0 0 300px;/*  take exact 300px width */
}
```

# 3)Css Grid
1. main idea is that we divide container element into rows and columns that can be filled with its child elements.
2. grid lines one more then columns and rows.

```css
.container--1 {
  display:grid;
  grid-template-columns: repeat(4, 1fr); /* All 4 columns are of same width */
}

.el--2{
  grid-column: 1 / span 4; /* span 1 column to 4 column */
  grid-column:1/-1;   /* span 1 column to 4 column(all column) */
}

/* project implementation */
/* CSS GRID LAYOUT */
.container {
  display: grid;
  grid-template-columns: 1fr 300px;
  column-gap: 75px;
  row-gap: 60px;
  align-items: start;
}

.main-header {
  /* grid-column: 1 / span 2; */
  grid-column: 1 / -1; /* takes all the width two columns */
}

```
