block elements take the entire line, eg, (paragraphs, divs) etc, even if you set width it still takes entire line.

inline-block elements take as much space it needs not entire line. eg, images 

inline elements are basically text elements, they appear within a line of text. eg, strong, underline

css display property lets us change block elements to inline block

div is just a box

when we have multiple texts like video caption, channel name and video stats we want them to be on same line
but while also not taking the entire line, so to solve this problem we put them in a contained so they take up 
their entire line in container and not the entire page

div is also a block element, but we can fix that by display: inline-block 
div by default take 100% of the space

images by default overflow, the container doesnt matter

why grid over inline-block? grid maintains alignment much better

the issue with images is that they always take their original shape even inside a container. for them to take the
space of the container you have to set "width: 100%;"

object-fit: Contain: Scales the image so that the entire image is visible within the container
object-fit: Cover: Scales the image so that the entire container is filled.


flexbox is similar to grid just a bit more flexible.
.div {
    display: flex;
    flex-direction: row;
}
vertical alignment is maintained by default
flex: 1 property is equivalent to 1fr in grid
the layout in grid is more rigid like the size is defined in the outer div but here each div can be sized individually

justify-content: center; # puts all items in center
justify-content: start; # puts all items in start
justify-content: space-between; # seperates item with equal space

align-items: center/ start/ end/ stretch (default) - aligns the item in div either at top center or bottom or stretch it to fit the div


margin-left: -1px;

box-shadow: inset 1px 2px 3px rgba(0,0,0,0.05); (inside or outside, left right, top bottom, blur radius, color)

flex-shrink: 0; - is a special property of flexbox that makes it not shrink no matter what. it will retain its defined width

width: 0; - it makes the search bar (which has fix minimum width by default) shrink to max.

overflow: hidden; - makes the box/element content flowing outside curved body disappear

whenever we see an element on top of another element thats using CSS POSITON. it adds another dimension to our page

position: static; is the default as if it wasnt there

position: fixed; element no longer takes space on the page its floating above the page

top: 20px; distance from top of the browser window
left: 0px;

when left and right are used simultaneously the element will stretch to satisfy both
we can use top left etc along with width and height. if we wanna resize the element based
on window resizing then use left right and for fixed use width or height

since the content will get covered by the header/fixed element, we use PADDING in the body tag

position: absolute; is almost same as fixed, the same top, left right bottom attributes work

position: fixed - placed in the browser window (will stay there even if you scroll)
position: absolute - placed on the page (it will start to move up with the page as you scroll)

now the issue with position element is that when two elements overlap, the element defined below
will overshadow the element defined first. to overcome this:
z-index: 1; - which means the z-index of element defined first is higher so it will overshadow the 
element defined later on

whenever position: absolute; element is inside position: fixed; element its (top, left, bottom etc) is
gonna be relative to the position: fixed; element and not the page (which is the normal case scenario)

as of now we have fixed and absolute which doesnt move as we scroll but what if we want to design something
like the duration in yt thumbnail, it is fixed on the thumbnail yet moves as we scroll along with thumbnail
for that we use position: relative; because position: fixed; ke andar absolute dalenge to wo absolute wala
bhi usme fix hi ho jayega and itll not move as wel scroll.

position: relative; - displays the element as normal except if we put position absolute here
itll position it relative to the element instead of the page

the rule of which element was written first do not apply to position: static; which is default
but apart from static it applies to any other positon

div just creates a box for whatevers inside so we can create a div and use postiion: relative and absolute

tooltip - we can use opacity:0; and hover properties to make tooltips.
pointer-events: none; - disables hovering etc.
transition: which howlong:
white-space: nowrap; used when text is wrapping around and not in single line








.thumbnail{
    width: 300px;   /*the heigh will auto adjust*/
    height: 300px;
    object-fit: contain; /*this decides what happens if the heigh and width doesnt match image ratio*/
    object-position: bottom;
    border-width: 2px;
    border-color: red;
    border-style: solid;
}

.search-bar{
  font-size: 33px;
  margin-left: 34px;
}


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
