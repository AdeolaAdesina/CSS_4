# CSS_4 Display and positioning

# Flow of HTML
A browser will render the elements of an HTML document that has no CSS from left to right, top to bottom, in the same order as they exist in the document. 

This is called the flow of elements in HTML.

In addition to the properties that it provides to style HTML elements, CSS includes properties that change how a browser positions elements. 

These properties specify where an element is located on a page, if the element can share lines with other elements, and other related attributes.

In this lesson, you will learn five properties for adjusting the position of HTML elements in the browser:

- position
- display
- z-index
- float
- clear

Each of these properties will allow us to position and view elements on a web page. They can be used in conjunction with any other styling properties you may know.


Here's the html and css files for this class:

index.html:

```
<!DOCTYPE html>
<html>
<head>
  <title>Please Participate in Our Survey!</title>
  <link href="https://fonts.googleapis.com/css?family=Oswald:300,700|Varela+Round" rel="stylesheet">
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <header>
    <ul>
      <li>Question 1</li>
      <li>Question 2</li>
      <li>Question 3</li>
      <li>Question 4</li>
      <li>Question 5</li>
    </ul>
  </header>
  
  <div class="welcome">
    <h1>Welcome to our survey!</h1>
    <p>We're looking forward to getting your answers so we can make sure our products and services are the best they can be!</p>
  </div>

  <div class="question">
    <h4>Question 1</h4>
    <h2>I like participating in physical activity such as running, swimming, or biking.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

  <div class="question">
    <h4>Question 2</h4>
    <h2>I try to keep up to date with the latest fashion in active wear.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

  <div class="question">
    <h4>Question 3</h4>
    <h2>I purchase clothing online regularly.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

  <div class="question">
    <h4>Question 4</h4>
    <h2>I try to buy goods that are designed and/or manufactured in my home country.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

  <div class="question">
    <h4>Question 5</h4>
    <h2>I look to famous athletes when trying to choose what to wear when training.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

</body>
</html>
```

style.css:

```
body {
  background-color: #FFF;
  margin: 0 auto;
}

header {
  background-color: #466995;
  border-bottom: 1px solid #466995;
}

ul {
  margin: 30px auto;
  padding: 0 20px;
  text-align: center;
}

li {
  color: #FFF;
  font-family: 'Oswald', sans-serif;
  font-size: 16px;
  font-weight: 300;
  text-transform: uppercase;
}

li:hover {
  color: #DBE9EE;
}

h1 {
  color: #466995;
  font-family: 'Oswald', sans-serif;
  font-size: 32px;
  font-weight: 300;
  text-transform: uppercase;
}

h2 {
  color: #333;
  font-family: 'Varela Round', sans-serif;
  font-size: 26px;
  font-weight: 100;
  margin: 0 auto 20px auto;
}

h3 {
  color: #466995;
  font-family: 'Oswald', sans-serif;
  font-size: 18px;
  text-align: center;
  font-weight: 700;
  text-transform: uppercase;
  padding: 30px;
}

h4 {
  color: #466995;
  font-family: 'Oswald', sans-serif;
  font-size: 18px;
  font-weight: 300;
  letter-spacing: 2px;
  text-align: center;
  text-transform: uppercase
}

p {
  color: #333;
  font-family: 'Varela Round', sans-serif;
  font-size: 18px;
}

footer {
  background-color: #DBE9EE;
  text-align: center;
}

.welcome {
  background-color: #DBE9EE;
  box-sizing: border-box;
  padding: 40px;
  text-align: center;
  width: 100%;
}

.question {
  text-align: center;
}

.answer {
  border: 1px solid #466995;
  margin: 20px;
}

.answer:hover {
  background: #C0D6DF;
  color: #FFF;
}
```


# Position

Take a look at the block-level elements in the image below:

![Screenshot_145](https://user-images.githubusercontent.com/29931071/200356974-0bb8f86c-d10f-4217-b3fa-b128dfd034b3.png)


Notice the block-level elements in the image above take up their own line of space and therefore don’t overlap each other. 

In the browser to the right, you can see block-level elements also consistently appear on the left side of the browser. This is the default position for block-level elements.

The default position of an element can be changed by setting its position property. The position property can take one of five values:

- static - the default value (it does not need to be specified)
- relative
- absolute
- fixed
- sticky


## Class work

In style.css, add a declaration to the .question ruleset that sets the position to static.

Notice that setting position to static does nothing. That’s because static simply refers to the default behavior.


style.css:

```
.question {
  text-align: center;
  position: static;
}
```

# Position: Relative

One way to modify the default position of an element is by setting its position property to relative.

This value allows you to position an element relative to its default static position on the web page.

```
.green-box {
  background-color: green;
  position: relative;
}
```

Although the code in the example above instructs the browser to expect a relative positioning of the .green-box element, it does not specify where the .green-box element should be positioned on the page. 

This is done by accompanying the position declaration with one or more of the following offset properties that will move the element away from its default static position:

- top - moves the element down from the top.
- bottom - moves the element up from the bottom.
- left - moves the element away from the left side (to the right).
- right - moves the element away from the right side (to the left).


 It’s also important to note that offset properties will not work if the element’s position property is the default static.
 
 ```
 .green-box {
  background-color: green;
  position: relative;
  top: 50px;
  left: 120px;
}
```


In the example above, the element of green-box class will be moved down 50 pixels, and to the right 120 pixels, from its default static position. The image below displays the new position of the box.

![Screenshot_146](https://user-images.githubusercontent.com/29931071/200358675-4305daa8-933f-42d0-a9a9-9089ff02b1c8.png)


## Class work

`1 In style.css, inside the .question ruleset, change the position property to relative.

2 Next, in style.css, offset .question 40 pixels from the top.


style.css:

```
.question {
  text-align: center;
  position: relative;
  top: 40px;
}
```


# Position: Absolute

Another way of modifying the position of an element is by setting its position to absolute.

When an element’s position is set to absolute, all other elements on the page will ignore the element and act like it is not present on the page. 

The element will be positioned relative to its closest positioned parent element, while offset properties can be used to determine the final position from there. 

Take a look at the image below:

![Screenshot_147](https://user-images.githubusercontent.com/29931071/200359743-10ad0b0d-65f9-43f8-bf32-5adee816a0d7.png)


The “This website is in progress. Please come back later!” text is displaced from its static position at the top left corner of its parent container. 

It has offset property declarations of top: 300px; and right: 0px;, positioning it 300 pixels down, and 0 pixels from the right side of the page.


## Class work

1 In style.css, set the position inside of the header ruleset to absolute.

Notice how it’s now removed from the normal flow of the document, and covering the welcome section.

2 When you changed the position to absolute, you may have noticed that the header shrunk horizontally. 

We’ll learn why in a later exercise. For now, set the width property of the header to 100%.


style.css:

```
header {
  background-color: #466995;
  border-bottom: 1px solid #466995;
  position: absolute;
  width: 100%;
}
```


# Position: Fixed

When an element’s position is set to absolute, as in the last exercise, the element will scroll with the rest of the document when a user scrolls.

We can fix an element to a specific position on the page (regardless of user scrolling) by setting its position to fixed, and accompanying it with the familiar offset properties top, bottom, left, and right.

```
.title {
  position: fixed;
  top: 0px;
  left: 0px;
}
```

In the example above, the .title element will remain fixed to its position no matter where the user scrolls on the page, like in the image below:

![Fixed](https://user-images.githubusercontent.com/29931071/200360995-de22907a-7a82-4481-8702-08286257ca60.gif)

This technique is often used for navigation bars on a web page.


## Class work

1 In style.css, change the position property inside of the header rule to fixed. Scroll up and down the web page. What do you notice?

2 Notice that part of the “Welcome” section is now covered up by the header. That’s because when we changed the position of the header to fixed, we removed it from the flow of the html document. Let’s fix that. Set the position of the .welcome element to relative.

3 Offset the “Welcome” section by 200 pixels from the top. Everything might not be displaying correctly just yet; we’ll fix it in a later exercise.


style.css

```
header {
  background-color: #466995;
  border-bottom: 1px solid #466995;
  position: fixed;
  width: 100%;
}


.welcome {
  background-color: #DBE9EE;
  box-sizing: border-box;
  padding: 40px;
  text-align: center;
  width: 100%;
  position: relative;
  top: 200px;
}
```



# Position: Sticky

The sticky value is another position value that keeps an element in the document flow as the user scrolls, but sticks to a specified position as the page is scrolled further. 

This is done by using the sticky value along with the familiar offset properties, as well as one new one.

```
.box-bottom {
  background-color: darkgreen;
  position: sticky;
  top: 240px;
}
```


In the example above, the .box-bottom <div> will remain in its relative position, and scroll as usual. When it reaches 240 pixels from the top, it will stick to that position until it reaches the bottom of its parent container where it will “unstick” and rejoin the flow of the document.

![Sticky](https://user-images.githubusercontent.com/29931071/200362609-4d59b970-301b-4da9-bf79-97b0380890b6.gif)


## Class work

Inside style.css, change the position of the elements with the class question to sticky.


style.css:

```
.question {
  text-align: center;
  position: relative;
  top: 40px;
  border: 15px solid #DBE9EE;
  background-color: white;
  position: sticky;
}
```


# Z-Index

When boxes on a web page have a combination of different positions, the boxes (and therefore, their content) can overlap with each other, making the content difficult to read or consume.

```
.blue-box {
  background-color: blue;
}
 
.green-box {
  background-color: green;
  position: relative;
  top: -170px;
  left: 170px;
}
```

In the example above, the .green-box element overlaps on top of the .blue-box element.

The z-index property controls how far back or how far forward an element should appear on the web page when elements overlap. 

This can be thought of as the depth of elements, with deeper elements appearing behind shallower elements.

The z-index property accepts integer values. Depending on their values, the integers instruct the browser on the order in which elements should be layered on the web page.

```
.blue-box {
  background-color: blue;
  position: relative;
  z-index: 1;
}
 
.green-box {
  background-color: green;
  position: relative;
  top: -170px;
  left: 170px;
}
```

![Screenshot_148](https://user-images.githubusercontent.com/29931071/200363671-2c24c8bf-a97c-40cc-a057-ff3ee3d6803b.png)


## Class work

In style.css, set the z-index of the header to 10. Notice how the header is no longer covered by other elements when you scroll!

style.css:

```
header {
  background-color: #466995;
  border-bottom: 1px solid #466995;
  position: fixed;
  width: 100%;
  z-index: 10;
}
```


# Inline Display

Every HTML element has a default display value that dictates if it can share horizontal space with other elements. Some elements fill the entire browser from left to right regardless of the size of their content. Other elements only take up as much horizontal space as their content requires and can be directly next to other elements.

In this lesson, we’ll cover three values for the display property: inline, block, and inline-block.
