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

### HTML

We've been changing HTML for this Instagram page.  HTML codes the content and structure of a webpage.

# Style

### Username color

1. Right click on the username and choose "Inpect Element" again or navigate to that part of the code.
2. Look to the right for code that says

        .upuiUsername, .upuiUsername a, .upuiUsername a:visited {
            color: #111;
        }
with a color box next to it.
3. Click on the color box, and a color selector will pop up.  Pick any color you like.

### Change the big header background color

1. Right click on the dark gray part of the header.

2. Look to the right for code that says

        element.style {
        }
3. Add

        background: linear-gradient(red,blue);
inside the brackets.

4. The background is now crazy.  Click on the color boxes for the red and blue and change them to your liking.

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
2. Delete.

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
        for(i = 0; i < images.length; i ++){
            $(images[i]).animate({marginLeft: i*100},1000 * i);
        }

### JavaScript

We were able to manipulate things on our page using a language called JavaScript.  In this case, we use something called jQuery to help us select different parts of our page and change them.


# Inspiration

For examples of neat things and code that made them, check out http://codepen.io/.
