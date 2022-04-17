# immaterial-css

Yet another self-created css file. It has very little layout settings but it's mostly for styling.

Inspired by and some of it ripped from [Tania Rascia's Primitive CSS framework](https://github.com/taniarascia/primitive).

## Some Guidelines

* I like flexbox for those times when I have an unknown number of rows or columns. It handles those nicely.

* I like grid when I have a very good idea of how many columns (or rows) I'll need for elements. It's still "flexible" however in case you need to resize.

* I like bigger fonts in some things (for instance where it needs to be bigger like headings and such). I prefer "quieter" font styles for paragraphs or li element text.

* In my "widgets" I like padding :-) but not necessarily bigger fonts. Do what you will.

## How to use?

Download the styles.css file to a place you can import it into your html page. It will take of the rest itself.

For simple nav links, try something like this:

```html
<ul class="nav">
    <li class="nav first"><a class="nav" href="#">Home</a></li>
    <li class="nav"><a class="nav" href="#">Contact</a></li>
    <li class="nav"><a class="nav" href="#">About</a></li>
    <li class="nav right last"><a class="nav" href="#">Login</a></li>
</ul>
```

## Some Commentary

### html

Setting a decent line-height below for your whole page. Feel free to adjust.

```css
html {
  line-height: 1.3;
}
```

### body

Sets the height to 100% for view-height. The display uses flexbox. So, all direct child blocks are rendered in column fashion. Setting flex-direction to something other than "column" will make things look ... err ... funky. Consider not doing it.

I prefer Open Sans but feel free to change it to whatever you like.

```css
body {
  margin: 0;
  height: 100vh;
  display: flex;
  flex-direction: column;
  font-family: 'Open Sans', sans-serif;
}
```

### headings

I like my h1's kinda big. The other h(n)'s ... not so much.

```css
h1 {
  font-size: 2rem;
}
```

### nav's

If you prefer to use "nav", I have it set to a nice dark color (not quite black though).

```css
nav {
  background-color: #383838;
}
```

I let ul handle the "nav" really and use flexbox.

```css
ul.nav {
  display: flex;
  list-style: none;
  background-color: #383838;
}
```

The following allows a li.nav element to take up all space within the parent ul but show in the center.

```css
li.nav {
  width: 100px;
  text-align: center;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 0.25rem;
  padding-bottom: 0.25rem;
}
```

I also like a nice bg-color change on hover on the nav links :-)

```css
li.nav:hover {
  background-color: gray;
}
```

The li.right is for the far right li element that will be aligned to the ... right.

```css
li.right {
  margin-left: auto;
}
```

This is set so that first li element is not too far margin-ed from the left.

```css
li.first {
  margin-left: -1.4rem;
}
```

Likewise, the last element on the right should have some space before running into the right side of the page.

```css
li.last {
  margin-right: 1rem;
}
```

Since my nav links usually have a dark background, I like them to show up as very light colored.

```css
a.nav, a.nav:visited {
  color: white;
}
```

### section

I like to use ```<section>``` within a div and give the child content some padding.

```css
section {
  padding: 1rem;
}
```

Consider this one optional. Normally, you wouldn't underline a heading but I have it here just for my demo page. Use this one with ```<h(n)>``` tag.

```css
.section-head {
  text-decoration: underline;
}
```

### hyperlinks

Below are my normal link "a"'s.

```css
a, a:visited {
  color: gray;
  font-weight: 600;
  text-decoration: none;
}

a:hover {
  color: gray;
  font-weight: 900;
  text-decoration: underline;
}
```

### button

Still not sure if I'm going to stick with these button stylings or not.

```css
button {
  padding: 0.3rem 1.1rem 0.3rem 1.1rem;
  font-family: inherit;
  border-radius: 5px;
}
```

### content text

This is where I take the content text and make it just a tad lighter. Not too much though because my sight is beginning to dwindle a bit.

```css
p, li, pre, td, th {
  opacity: 0.85;
}
```

### table

Shamelessly took these tables (and if you look over the whole css page, you'll see many other things too) from Tania Rasica's primitive css stylings.

```css
table {
  margin: 0 0 1.5rem 0;
}

table {
  border-collapse: collapse;
  border-spacing: 0;
  width: 100%;
  max-width: 100%;
}

thead th {
  border-bottom: 2px solid #dedede;
}

tfoot th {
  border-top: 2px solid #dedede;
}

td {
  border-bottom: 1px solid #dedede;
}

th,
td {
  text-align: left;
  padding: 0.5rem;
}

caption {
  padding: 1rem 0;
  caption-side: bottom;
  color: #ababab;
}

.striped-table tbody tr:nth-child(odd) {
  background-color: #f8f8f8;
}

.contain-table {
  overflow-x: auto;
}
```

### input widgets

Adding some border-radius and padding to the input widgets:

```css
input[type=text],
input[type=password],
input[type=url],
input[type=email],
input[type=tel],
input[type=number],
input[type=search],
select,
textarea {
  border-radius: 4px;
  padding: 4px;
  font-family: inherit;
}

button,
input,
optgroup,
select,
textarea {
  font-family: inherit;
  font-size: 100%;
  line-height: 1.15;
  margin: 0;
}

select {
  color: #404040;
  -webkit-appearance: none;
  -moz-appearance: none;
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABIAAAAJCAYAAAA/33wPAAAAvklEQVQoFY2QMQqEMBBFv7ERa/EMXkGw11K8QbDXzuN4BHv7QO6ifUgj7v4UAdlVM8Uwf+b9YZJISnlqrfEUZVlinucnBGKaJgghbiHOyLyFKIoCbdvecpyReYvo/Ma2bajrGtbaC58kCdZ1RZ7nl/4/4d5EsO/7nzl7IUtodBexMMagaRrs+06JLMvcNWmaOv2W/C/TMAyD58dxROgSmvxFFMdxoOs6lliWBXEcuzokXRbRoJRyvqqqQvye+QDMDz1D6yuj9wAAAABJRU5ErkJggg==) right center no-repeat;
  line-height: 1;
}

select::-ms-expand {
  display: none;
}

button,
select {
  text-transform: none;
}

select {
  padding-right: 2rem;
}

[type='checkbox'],
[type='radio'] {
  box-sizing: border-box;
  padding: 0;
}

fieldset {
  padding: 0.35em 0.75em 0.625em;
}

legend {
  box-sizing: border-box;
  color: inherit;
  display: table;
  max-width: 100%;
  padding: 0;
  white-space: normal;
}

fieldset {
  border: 1px solid #dedede;
  border-radius: 4px;
  padding: 1rem;
  margin: 1.5rem 0;
}

legend {
  padding: 0 0.5rem;
  font-weight: 600;
}
```

### misc

Blockquote stuff ...

```css
blockquote {
  margin: 0 0 1.5rem 0;
  border-left: 16px solid #e2e2e2;
  padding: 0 1.5rem;
  font-size: 1.5rem;
  font-style: italic;
}

blockquote cite {
  display: block;
  margin-top: 1.5rem;
  font-size: 1rem;
  text-align: right;
}
```

### footer

The magic of making the footer stay at the bottom even when there's no filler content and it's without vertical scrollbars, is to use flexbox and set margin-top to auto.

```css
footer {
  margin-top: auto;
  background-color: #383838;
  color: white;
  font-size: smaller;
  text-align: center;
}
```

### pre

For making pre behave when I really horizontally squish the page.

```css
pre {
  white-space: pre-line;
}
```

### other

Still not quite sure what this does yet.

```css
@media (min-width: 600px) {
  .contain-table {
    width: 100%;
  }
}
```
