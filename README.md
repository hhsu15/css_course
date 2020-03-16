# CSS learning

## CSS cascade and specificity

CSS determines what to render when there is conflicting of sysle for an element by a set of rules. It's called cascade. It looks like at the selectors in the following order:

- inline style
- id
- class
- element

And then count each specificity (composed with selector and declaration block) with (inline, id, class, element). The one specificity with higher order will win. One id is more important than 1000 classes so you get the idea.

A pseudo class (something like .btn:hover) is also considered as class count.

## Relative to Absolute

Use percentage relative to the parent's element size.
When computing percentage of a child element for length (width, height, padding etc), it's always relative to the parent's "width".
So for example the a `padding: 10%` of child element, will have 100px when the parent element has `width: 1000px`.

### em and rem (font-based)

For font-size, `em` uses the parent element size as reference.

- `font-size: 3 em` -> 72 px when parent's font size is 24px

For length (padding, width, height etc) size, `em` uses the current element font size as reference.

- `padding: 3 em` -> 48 px when current element font-size is 24px

when using `rem`, it's alwasy referencing the root font-size as refefence, for example:

- `font-size: 3 rem` -> 48px when root font-size is 16

### vh and vw (viewport based)

- 90vh -> 90% of the current vewiport height
- 80vw -> 80% of the current viewport width

### Set your root font size using html selectot

This is very cool technieque!! Set your root font-size and use `rem` everywhere rather hard coding the `px`. We are goint to set the root font size to `font-size: 65.5%` since by default it's 16 px, this translates to 10 px by default and it responeds to the size of the browser.

# Visual Formatting Model

## Box Model

Element represented as a box model, which is made of:

- margin: space between boxes
- border: goes around the padding the content
- padding: white spaces around the content
- width: width of thr content
- height: height of the content
- content: text, img, etc
- filled area: the entire box to be filled

When use `box-sizing: border-box`, the specified width and height will be applied to the box model, as opposed to the `content`. So the above elements will be adjusted automatically.

There are four types: Inline, Block-level, Inline-Block.

### Block-Level Box

Elements formatted visually as blocks. Showing contents in mutiple lines.

- 100% parents' width
- Vertically, one after another with line breaks
- Block type are displyed using `display` property:

```css
display: block;
/* other display values which also produce block level elements:  
display: list-item;
display: flex;
display: table;
*/
```

### Inline Box

Showing contents in one line

- Content is distributed in lines
- occupies only content's space
- No line breaks!!
- No heights and widths
- Paddings and margins only horizontal (left and right)

```csss
display: inline;
```

### Inline-Block Box

Showing contents as boxes horizontally

- A mix of block and inline
- Occupies only content's space
- No line-breaks
- Box-model applies as showed

```css
display: inline-block;
```

## Positioning Schemes

Normal flow, Absolute positioning and Floats

### Normal flow

If you don't specify, or use relative then it's a normal flow.

Default is `position: relative`

### Floats

Element is removed from the normal flow.

```
float: left
float: right
```

### Absolute Positioning

Element is removed from the normal flow

- No impage on the surrounding content or elements
- we use `top`, `bottom`, `left`, `right` to offset the elemet from its relative positioned container.

```
position: absolute
position: fixed
```

## BEM (Block Element Modifier)

- Block: standalone component that is meaningful on its own
- Element: part of block that has no standalone meaning
- Modifier: a different version of a block or an element

It looks like this:

```css
.my-block {
}
.my-block__element {
}
.my-block__element--modifier {
}
```

## The 7-1 Pattern for css architect

7 different folders for partial Sass files and 1 main Sass file to import all other files into a compiled CSS stylesheet

## SASS

Preprocessor for CSS, which then gets compiled to css file. Using Sass, you will have the ability to do things like:

- variables
- nesting
- operators
- partials and imports
- mixins: write reusable pieces of css code
- functions
- extends
- control directives: if statements etc

Refer to examples.

**------------------------Course set up ------------------------------**

# Course Material and FAQ for my Advanced CSS Course

This repo contains starter files and the finished project files for all the projects contained in the course.

Plus, I made all the [course slides available for download](slides-students-C04.pdf), to make it easier to follow along the conceptual videos.

👇 **_Please read the following Frequently Asked Questions (FAQ) carefully before starting the course_** 👇

## FAQ

### Q1: How do I download the files?

**A:** If you're new to GitHub and just want to download the complete package, hit the green button saying "Clone or download", choose the "Download ZIP" option, and you're good to go.

### Q2: One of the NPM packages is not working (compiling Sass, live-reload, etc). How to fix it?

Unfortunately, this is quite common. I listed some possible fixes [in this document](npm-fixes.md).

### Q3: I'm stuck in one of the projects. Where do I get help?

**A:** Have you extensively tried fixing the problem on your own? If you failed at fixing it, please **post a detailled description of the problem to the Q&A area of that video over at Udemy**, along with a [codepen](https://codepen.io/pen/) containing your code. You will get help as fast as possible! Please don't send me a personal message or email to fix coding problems.

### Q4: You keep mentioning your resources page. Where can I find it?

**A:** It's on my website at <http://codingheroes.io/resources>. You can subscribe for updates 😉

### Q5: What VSCode theme are you using?

**A:** I use Oceanic Next (dimmed bg) for all my coding and course production. [Here is my complete VSCode setup](vscode-setup.md).

### Q6: You use codepens in some of the lectures. Where can I find them?

**A:** They are all available on my [public codepen profile](https://codepen.io/jonasschmedtmann/pens/public/). The ones you're looking for might be buried under some newer ones.

### Q7: Can I see a final version of the course projects?

**A:** Sure, I have an online version of all three. Here they are: [Natours](https://natours.netlify.com) (advanced CSS, Sass and responsive design), [Trillo](http://trillo.netlify.com/) (flexbox) and [Nexter](https://nexter.netlify.com/) (CSS Grid).

### Q8: Videos don't load, can you fix it?

**A:** Unfortunately, there is nothing I can do about it. The course is hosted on Udemy's platform, and sometimes they have small technical issues like this one. Please just come back a bit later or [contact their support team](https://support.udemy.com/hc/en-us).

### Q9: Videos are blurred / have low quality, can you fix it?

**A:** Please open video settings and change the quality from 'Auto' to another value, for example 720p. If that doesn't help, please [contact the Udemy support team](https://support.udemy.com/hc/en-us).

### Q10: Are the videos downloadable?

**A:** Yes, I made all videos downloadable on the Udemy platform so you can learn even without an internet connection. To download a video, use the settings icon in the right bottom corner of the video player.

### Q11: I love your courses and want to get updates on new courses. How?

**A:** First, you can subscribe to my email list [at my website](http://codingheroes.io/newsletter). Plus, I make important announcements on twitter [@jonasschmedtman](https://twitter.com/jonasschmedtman), so you should definitely follow me there 🔥

### Q12: How do I get my certificate of completion?

**A:** A certificate of completion is provided by Udemy after you complete 100% of the course. After completing the course, just click on the "Your progress" indicator in the top right-hand corner of the course page. If you want to change your name on the certificate, please [contact the Udemy support team](https://support.udemy.com/hc/en-us).

### Q13: Do you accept pull requests?

**A:** No, for the simple reason that I want this repository to contain the _exact_ same code that is shown in the videos. However, please feel free to add an issue if you found one.
