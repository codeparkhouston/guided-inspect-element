# Peaking into the code

Sometimes it really helps to open something up to see what's going on.  The "Inspect Element" tool let's us do just that for webpages!  It's like opening the hood of a car, working backwards on a math problem, or reading a recipe for grandma's chicken soup.

**Let's try it on your school's webpage!**

Go to: [http://www.houstonisd.org/Domain/22556](http://www.houstonisd.org/Domain/22556)

# I. Content

The code we are changing in the section will be in the box on the left.

### Change the name of your school!

1. Right click on "Charles H. Milby High School" at the top.
2. Choose "Inspect Element" from the menu.  A window with code will show on the bottom or on the side.
3. The highlighted line is the code for the heading.  Change the text that says "Charles H. Milby High School" to anything you want!


### Move the header around

1. Right click on the side of the gold header up top.
2. Choose "Inspect Element" from the menu as before.  The code for this header will be highlighted.
3. Click and drag this code to some other place in the code, such as after:

        <div id="hp-page-outer"></div>


### Change the slider picture

1. Right click on the picture in the center.
2. This will highlight code that says:

       <a class="image-overlay"></a>

3. Go up 3 lines to:

      <div class="rotating-images"></div>

4. Click on the arrow on the left next to this line.  This will open up the code for this section.

5. Click on the arrow on the left next to this next line as well:

       <ul class="pictures"></ul>

6. We now get to see the code for the picture "gallery".  If we wait, we'll see the code updating!  How are the images fading in and out?

7. Open up the code in:

        <li class="active" index="0" style="...">...</li>

8. Open up the code in:

        <a class="imgHolder" target="_self" href="#" index="0"></a>

9. Double-click on ```img src``` and change out the link in src="" to: [http://goo.gl/q01YFQ](http://goo.gl/q01YFQ).

Phew. That was quite a bit of effort.  We'll see how to do this way quicker in a bit.

### HTML

We've been changing HTML for this webpage.  HTML codes the content and structure of a webpage.


# Style

### Username color

1. Right click on where your school name was and choose "Inpect Element" again or navigate to that part of the code.
2. Look to the right for code that says

        element.style {
            color: rgb(255, 255, 255);
        }
with a color box next to it.
3. Click on the color box, and a color selector will pop up.  Pick any color you'd like.

### Change the big header background color

1. Right click on the side of the golden header.

2. Look to the right for code that says
    element.style {
        background-color: rgb(180, 108, 0);
    }
3. Add

        background: linear-gradient(red,blue);
inside the brackets.

4. The background is now crazy.  Click on the color boxes for the red and blue and change them to your liking.

5. For extra effect, click on the HTML line of code that says:

        <div id="gb-top-bg" style="background-color: rgb(0, 51, 102);"></div>
6. Go to the color box for the background-color on the right and change the color.





### Rotate a picture

1. Click on a picture.
2. Right click on the picture and choose "Inspect Element."
3. Look to the right for the code that says

        element.style {
            background-image: url(http://photos-d.ak.instagram.com/hphotos-ak-xaf1/t51.2885-15/10958626_808888062520027_914160921_n.jpg);
        }
4. Click on the second } and add

        -webkit-transform: rotate(120deg);
5. Experiment with the number of degrees.

### Background image
1. Right click on the phone and "Inspect Element."
2. Look to the right for the code:

        .page-home .home-phones{
            background: url(//instagramstatic-a.akamaihd.net/bluebar/c4b4b0a/images/homepage/home-phones.png) no-repeat 0 80px;
            ...
3. Click on the checkbox next to ```background:...``` to uncheck it.

### Fading images
1. Right click and "Inspect Element" on the changing images.
2. We can now see the code. How are the images transitioning like a slide show?

### CSS
We just got to play around with how content looks in a webpage.  This is called, the 'style' and is often coded by something called CSS.

# More Control

### Deleting the phone pictures
1. Make sure the code

        <div id="iphone-overlay">
is selected.
2. Press "Delete".

### Hiding the phone pictures
1. Refresh the page.
2. Click on the "Console" tab where the code is.
3. Type

        $('#iphone-overlay').hide();
and press ```Enter``` to run the code!
4. Type

        $('#iphone-overlay').show();
and press ```Enter```.

### Adding borders on everything
1. Type

        $('*').css({border: '1px solid #000'});
and press ```Enter```.

### Animating and moving the pictures
1. Try

        $('#iphone-overlay').animate({marginLeft: '500px'}, 1000);
and press ```Enter```.

2. And

        $('#iphone-overlay').animate({marginLeft: '0px'}, 1000);
3. Let's move each picture

        var images = $('#iphone-overlay img');
        for ( count = 0; count < images.length; count ++ ){
            $(images[count]).animate( { marginLeft: count*100 }, 1000 * count);
        }

### JavaScript

We were able to manipulate things on our page using a language called JavaScript.  In this case, we use something called jQuery to help us select different parts of our page and change them.


# Inspiration

For examples of cool things and the code that made them, check out http://codepen.io/.
