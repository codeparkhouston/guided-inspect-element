You can also see this guide online at: [https://github.com/codeparkhouston/guided-inspect-element](https://github.com/codeparkhouston/guided-inspect-element)

# Peeking into the code

Sometimes it really helps to open something up to see what's going on.  The "Inspect Element" tool lets us do just that for webpages!  It's like opening the hood of a car, working backwards on a math problem, or reading a recipe for your favorite dessert.

**Let's try it on your school's webpage!**

Go to: [http://www.houstonisd.org/milby](http://www.houstonisd.org/milby)

# I. Content

The code we are changing in the section will be in the box on the left.

### A. Change the name of your school!

1. Right click on "Charles H. Milby High School" at the top.
2. Choose "Inspect Element" from the menu.  A window with code will show on the bottom or on the side.
3. The highlighted line is the code for the heading.  Change the text that says "Charles H. Milby High School" to anything you want!


### B. Move the header around

1. Right click on the side of the gold header up top.
2. Choose "Inspect Element" from the menu as before.  The code for this header will be highlighted.
3. Click and drag this code to some other place in the code, such as after:

        <div id="hp-page-outer"></div>


### C. Change the slider picture

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

### D. HTML

We've been changing HTML for this webpage.  HTML codes the content and structure of a webpage.


# II. Style

### A. Header color

1. Right click on where your school name was and choose "Inpect Element" again or navigate to that part of the code.
2. Look to the right for code that says

        element.style {
            color: rgb(255, 255, 255);
        }
with a color box next to it.
3. Click on the color box, and a color selector will pop up.  Pick any color you'd like.

### B. Change the big header background color

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


### C. Rotate something

1. Right click on "Houston East End's School of Choice since 1926."
3. Look to the right for the code that says

        element.style {
            color: rgb(255, 255, 255);
        }
4. Click on the second } and add

        -webkit-transform: rotate(20deg);
5. Experiment with the number of degrees.


### D. CSS
We just got to play around with how content looks in a webpage.  This is called, the 'style' and is often coded by something called CSS.


# III. More Control

On the tabs in the left box, click on the one that says "Console."  This is where we can write some JavaScript to interact with the page.

### A. Adding borders on everything
1. Type

        $('*').css({border: '1px solid #000'});
and press ```Enter```.

### B. Changing the images
1. Type 

        $('.rotating-images');
    and press ```Enter```.

    You will see some HTML code!

2. Type
        $('.rotating-images img');
    and press ```Enter```.

    These are all the images in the gallery.

3. Type
        $('.rotating-images img').length;
    and press ```Enter```.

    This will tell you how many pictures are in the gallery.

4. Put this code in the console:

        var petPictureLinks = [
            'http://i.imgur.com/lJMq1vL.jpg',
            'http://doge2048.com/meta/doge-600.png',
            'https://octodex.github.com/images/adventure-cat.png',
            'http://i.huffpost.com/gen/2364914/thumbs/o-GRUMPY-CAT-facebook.jpg',
            'https://octodex.github.com/images/baracktocat.jpg',
            'http://www.boothedog.net/wp-content/uploads/2011/07/Boo-the-dog-Hungry.jpg',
            'http://goo.gl/PBUw2X'
        ];

        $('.rotating-images img').each(function(iteration, imageElement){
            $(imageElement).attr('src', petPictureLinks[iteration]);
            console.log('What is the iteration?', iteration);
            console.log('What is the element?', imageElement);
            console.log('Where is the pet picture from?', petPictureLinks[iteration]);
        });


### C. Rotating things
1. Put this code in your console:

        var rotation = 0;

        jQuery.fn.rotate = function(degrees) {
            $(this).css({'-webkit-transform' : 'rotate('+ degrees +'deg)',
                         '-moz-transform' : 'rotate('+ degrees +'deg)',
                         '-ms-transform' : 'rotate('+ degrees +'deg)',
                         'transform' : 'rotate('+ degrees +'deg)'});
            return $(this);
        };

        var rotateStarburstInterval = setInterval(function(){
            rotation += 5;
            $('#gb-starburst').rotate(rotation);
        }, 100);

2. Rotate the logo like so:

        var logoRotation = 0;

        var rotateLogoInterval = setInterval(function(){
            logoRotation += 5;
            $('#gb-logo').rotate(logoRotation);
        }, 10);


### D. JavaScript
We were able to control and change these things on our page using a language called JavaScript.  In this case, we used something called jQuery to help us select different parts of our page and change them.


# Want to learn more?

Join us! Tell your teacher if you're interested in more info.
