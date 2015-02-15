# Peaking into the code

Sometimes it really helps to open something up to see what's going on.  The "Inspect Element" tool let's us do just that for webpages!  It's like opening the hood of a car, working backwards on a math problem, or reading a recipe for grandma's chicken soup.

**Let's try it on Instagram.**

I'm behind the times a bit so I don't use Instagram all that much, but I sure like looking at pictures of [dogs](http://instagram.com/mensweardog/).

Let's see what we can do.

# Content

### Change the username

1. Right click on the username "mensweardog"
2. Choose "Inspect Element" from the menu.  A window with code will show on the bottom or on the side.
3. The highlighted line is the code for the username.  Change the text that says "mensweardog" to anything you want!

### Change the number of followers

1. Follow the same steps as above for the number of followers.
2. Try it for any of the other text on the page, for example the text on the "Follow" button.


### Move the header around

1. Right click on the side of the blue header up top.
2. Choose "Inspect Element" from the menu as before.  The code for this header will be highlighted.
3. Click and drag this code to some other place in the code.

Pretty neat right? We've been changing HTML for this Instagram page.  HTML codes the content and structure of a webpage.

# Style

### Username color

1. Right click on the username and choose "Inpect Element" again or navigate to that part of the code.
2. Look to the right for code that says
```css
.upuiUsername, .upuiUsername a, .upuiUsername a:visited {
       color: #111;
}
```
with a color box next to it.
3. Click on the color box, and a color selector will pop up.  Pick any color you like.

### Change the big header background color

1. Right click on the dark gray part of the header.
2. Look to the right for code that says
```css
element.style {
}
```
3. Add
```css
        background: linear-gradient(red,blue);
```
inside the brackets.
4. The background is now crazy.  Click on the color boxes for the red and blue and change them to your liking.




#### Inspiration

http://codepen.io/
