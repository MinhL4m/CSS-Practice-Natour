--------header----------- use rem as value (unit bases on root font size)

background img(2 or 3 background at the sametime), background position, 

clip-path

transform and position absolute to make the title in the center

letter-spacing

::after (for the button)

TRICK: use transform: translateY(-<number>) to move the button up and down when hover and click.
	also use box-shadow: with blur to make it look closer and further (more blur looks further). when want it to closer, reduce the y axis and blur

--------animation for header-------
@keyframes
animation properties
animation-delay
animation-interation-count: <number> (to loop the animation number time)
animation-timing-function: (has some defined function also can use self-define functions)

At the end of the animation, it will be alittle shakie to the top. To fix, use:
	backface-visibility:hidden 

PORBLEM: when we put delay, the animation will show as normal before it start the animation.
FIX: animation-fill-mode: (auto apply the styles up to zero % of the animation before the animation start)


----- sass--------
use npm:
init the folder: npm init
instal sass: npm install sass
write scrip in package.json file
run scrip
7 - 1 pattern: 7 folder and 1 main file


----- custom grid with float--------
how to architect and build a simple grid system;
how the attribute selector work
how the :not pseudo-class work;
	:not(<another pseudo class>){} (.row:not(:last-child)) everything except last .row child


how calc() works, and what's the difference between calc() and simple Sass operations
	calc() can work to calculate in real time, Sass operation online before complipe 
	calc() can be use mix unit
	when calc() with sass variable, need to use #{<sass variabel>} (#{$max-width})


clearfix for float: 
	- use ::after of the parent element
	- display: table and clear:both

[alt="logo"]{css}: this mean select all the elements have alt="logo". This can apply to any thing such as src. 
	^="" mean we want the beggin of what we search match the value. 
	*="" mean we want any thing that contain the value

	
	
-----section about---------
background-clip (background for text effect) in _typography.scss
    background of the text: background-image
    display: inline-block;
    -webkit-background-clip: text;
    color: transparent;
    

transform multiple properties: skewX skewY

outline-offset property together with outline: 
    outline: is like make a border when hover
    outline-offset is the space between content and the outline

How to style elements that are not hovered while others are (in _composition.scss). use this for style the picture. When hover one, other not hover will scale down



-----feature section------

How to include and use an icon font 
Another way to creating the "skewed section" design (home.scss)
    instead of using clip-path we can use transform:skewY(deg) to make this effect

How and when to use the direct child selector (A > B, B is A children)

-----tour section----
roating card use:

 -perspective in CSS (_card.scss):
    perspective is to make the card move nicer look more real.
    perspective property has to be in the parent of the transform rotation element.
    the bigger the value, the less dramatic the effect gonna be.

 -backface-visibility property (_card.scss)
    when set this property to hidden, the backside of the card will not be visible.

Using background blend modes. use when we want the background to blend (_card.scss __picture):
    background-image: 2 image or linear and image.
    background-blend-mode: 
    This only apply for new browser (not IE and Edge)


How and when to use box-decoration-break
- Is for the card heading. (look at the card heading)


-------Stories Section--------
How to make text flow around shapes with shape-outside and float (stories.scss)
    shape-outside: property defines a shape—which may be non-rectangular—around which adjacent inline content should wrap.
    
    shape-outside only work with chrome and prefix for firefox.
    the element has to have dimention height and width
    
    the best way to move float is using transform.
    
How to apply a filter to images 
    filter can be use to blur and brightness for the picture

How to create a background video covering an entire section (use <video>)
    use video tag
    inside video tag use source tag for multiple source to make sure the browsers can run the video
    use z-index, position, opacity.
    Also on the video tag, has autoplay muted and loop for the effect


How and when to use the object-fit property
    object-fit:cover for the background video. This give the effect like the background-size:cover
    IMPORTANT:object-fit will make the element fill the entire parent while still mantaining its aspect ratio.part that not fit will be clip off.
    This property can work with image and video. 

--------booking section-------

How to implement "solid-color gradients"(_home.scss)
    layer of backgground image and set % for linear-gradient to make the affect

the general and adjacent sibling selectors (A + B) (_form)
    

How to use the ::-webkit-input-placeholder pseudo-element(_form)
    use to custom placeholder, only work on chrome and safari

How and when to use :focus, :invalid, placeholder-shown and :checked pseudo classes (form.scss)
    :focus:invalid  This will check for the field if it correct, if not it will follow the css

Techniques to build custom radio buttons (_form > __radio-button)
    There are no way to styling radio button, but we can hide it and make our own button.
    Use :checked to make the effect select (:checked can be use for checkbox and radio button)


---------Navigation bar----------
radial gradient: start from midle then go all the way outside

How to create custom animation timing fuctions using cubic bezier curves (background transition)
    - transition: <target> <time> cubic-bezier(<num>,<num>,<num>,<num>)

    - self define how the animation will react. 
    - easings.net : cheat sheet
    - cubic-bezier.com:  to make a custom on.
    - good to use in animation

How to animate "soild-color gradient" (Navigation hover effect)
    - use linear gradient deg to creat background first
    - use background-size to increate size and make part that we don't like temp disapeart
    - then use background-position to make it appear


Can use transparent to make element hidden


How and why to use transform-origin
    - Use to create animation.


-----pop up -------------
To make background go darken when the popup open and cant click any thing behind
create a big div to store the pop up. change the background color and move the z index to higher
(.popup)

How to create boxes with equal height using display: table-cell (__left and __right)
    - Instead of using float: left to make left and right container, we can use 
    display table cell for both left and right container.
    - The parent of both need to be display table
    - also can use vertical-align for table-cell to center it (__right)

How to create css text columns (__text)
    - Use column-count to specify number of columns
    - Use column-gap: to specify space gap
    - Use column-rule to specify the line between columns 

How to auto hyphenate words using hyphen. 
    - When it not enough space, the word may be break down into 2 pieces.
    - This give auto hyphen between 2 pieces
    - hyphens: auto

How to use :target pseudo class
    - This pseudo element active when the element is a target of a button or anchor
    - If people click on the button, the pop up will appear.
    - To close the popup, we move the target to anothe element(click another anchor or btn that target other) which make the popup not target any.
    It will lose all the css of target


========================= RESPONSIVE =========================
--Desktop first--
    - Start with CSS for desktop, large screen
    - Then media queries shrink design to smaller screens
    - easier way to learn

-- Mobile first--
    - Start writing CSS for mobile device
    - Then media queries expand design to a large desktop screen
    - Forces us to reduce website and app to absolute essentials 

------Media queries in Sass----------
    - instead of create on media and store every single class inside it, we
    can go into each class and write media query inside it.

Use mixin for media queries
    - Write media query in mixin file 

How to use the @content and @if Sass (mixin.scss)
    - @content allow us to pass a block of code into mixin
    -@if 
        + @mixin respond($breakpoint){
            @if $breakpoint == phone{
                @media(max-width: 600px){@content};;
            }
        }
    --> we can pass argument into mixin and use if to select

