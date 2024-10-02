
# Basic

Sample:
```html
<!DOCTYPE html>

<head>
<title> title </title>
<style>

h1{
color:blue
}

</style>
</head>

<body>

<h1 style="color:green">first title</h1>
<h1> second title</h1>
<h1>third title</h1>

</body>
```


# Inline styles
```html
<!DOCTYPE html>

<head>

<title> title </title>

</head>

  

<body>

<p style="color:dodgerblue; font-size:100px"> Test text 1</p>

  

<div style="color:red">Testing Text 2</div>

  

<p>asdf</p>

<p>asdf</p>

  

<div style="color:green">

<div style="color:yellow"> Test 3</div>

<div> Test 4 </div>

</div>

</body>
```



# Style Tag
```html
<!DOCTYPE html>

<head>

<title> title </title>

<style>

p{

color:red;

font-size:8px

}

div{

color:violet;

font-size:30px;

}

</style>

</head>

  

<body>

<p style="color:dodgerblue; font-size:100px"> Test text 1</p>

  

<div style="color:red">Testing Text 2</div>

  

<p>asdf</p>

<p>asdf</p>

  

<div style="color:green">

<div style="color:yellow"> Test 3</div>

<div> Test 4 </div>

</div>

</body>
```

#  Style external link

Save style tages as seperate file. E.g:
```css
p{

color:red;

font-size:8px;

}

div{

color:violet;

font-size:30px;

}
```


Modify the original to:
```html
<!DOCTYPE html>

<head>

<title> title </title>

<link rel="stylesheet" href="samplestyle.css">

</head>

  

<body>

<p style="color:dodgerblue; font-size:100px"> Test text 1</p>

  

<div style="color:red">Testing Text 2</div>

  

<p>asdf</p>

<p>asdf</p>

  

<div style="color:green">

<div style="color:yellow"> Test 3</div>

<div> Test 4 </div>

</div>

</body>
```

which would still lead to the same result


# Selection Classes and ID
Style sheet:
```css
#firstParagraph{

color:aliceblue;

font-size: 24px;

}

  
  

.red{

color:red;

}

  

.bigFont{

font-size:36px;

}

  

.blue{

color:blue;

}
```

```html
<!DOCTYPE html>

<head>

<title> title </title>

<link rel="stylesheet" href="samplestyle.css">

</head>

  

<body>

<p class="red bigFont"> Testing Text 1</p>

<div class="red">Testing Text 2</div>

  

<p class="blue">Testing Text 3</p>

<p class="bigFont">Testing Text 4</p>

<p id="firstParagraph"> Testing Text 5</p>

  
  

</body>
```

Remember: order of overriding matters!


# Coloring
Hex values of colors can be looked up in Mozilla developer network
```html
<!DOCTYPE html>

<head>

<title> title </title>

<style>

.green1{

color:green;

background-color:red;

}

.green2{

color:#00FF00;

background:red;

}

.green3{

color:rgb(0,255,0);

}

.green4{

color:rgba(0,255,0,0.7)

}

</style>

</head>

  

<body>

<p class="green1"> Testing Text 1</p>

<div class="green2">Testing Text 2</div>

  

<p class="green3">Testing Text 3</p>

<p class="green4">Testing Text 4</p>

<p> Testing Text 5</p>

  
  

</body>
```

*rgba*: alpha value paramaterizes opacity.



# Background Colors/Images

```html
<!DOCTYPE html>

<head>

<title> title </title>

<style>

body{

/* background-color: green;

background-image: url(CSS.png);

background-repeat: repeat-x;

background-position: top right;

background-attachment: fixed; */

  

background: aqua url(CSS.png) no-repeat right top;

  

}

</style>

</head>

  

<body>

<p > Testing Text 1</p>

<div >Testing Text 2</div>

  

<p >Testing Text 3</p>

<p >Testing Text 4</p>

<p> Testing Text 5</p>

  
  

</body>
```



# CSS Display Property

The *Display* CSS property defines the display type of an element, consisting of the two basic qualities of how an element generates boxes.

``` html
<!DOCTYPE html>

<head>

<title> title </title>

<style>

span{

display: block;

}

div{

display: inline;

}

li{

display: inline-block;

width: 100px;

height: 100px;

}

/* nav{

display: none;

visibility: hidden;

} */

</style>

</head>

  

<body>

<nav>

<ul>

<li><a href="#">Home</a></li>

<li><a href="#">Services</a></li>

<li><a href="#">About</a></li>

<li><a href="#">Contact</a></li>

</ul>

</nav>

<div>

<div>Hello World</div>

<span>Hello World</span>

<span>Hello World</span>

<span>Hello World</span>

</div>

  

</body>

</html>
```


# CSS for list items
``` html
<!DOCTYPE html>

<head>

<title> title </title>

<style>

li{

list-style:none;

}

</style>

</head>

  

<body>

<nav>

<ul>

<li><a href="#">Home</a></li>

<li><a href="#">Services</a></li>

<li><a href="#">About</a></li>

<li><a href="#">Contact</a></li>

</ul>

</nav>

<div>

<div>Hello World</div>

<span>Hello World</span>

<span>Hello World</span>

<span>Hello World</span>

</div>

  

</body>

</html>
```



# Exercise 1
```html
CSS Exercise #1 Source Code

Section 3, Lecture 81

<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<title> CSS Exercise 1 </title>

<link rel="stylesheet" type="text/css" href="samplestyle.css">

</head>

<body>

<header>

<nav>

<ul>

<li>Home</li>

<li>About</li>

<li>Contact</li>

</ul>

</nav>

</header>

<section>

<h2>Page Title</h2>

<p>First paragraph</p>

<p>second paragraph</p>

</section><section>

<h3>Section Heading</h3>

<p>First paragraph</p>

<p>second paragraph</p>

</section>

<footer>

<p>My company footer</p>

</footer>

</body>

</html>
```

``` css
body{

background-color:bisque;

}

li{

list-style: none;

display: inline-block;

background-color: red;

color: white;

}

section{

background-color: aliceblue;

}

footer{

background-color: darkgray;

color: white;

}
```


# CSS measures and  properties
Common units:
- Percentage
- Pixel Unit
- EM unit
- REM unit

``` html
<!DOCTYPE html>

<html lang="en">

<head>

<title> title </title>

<style>

div{

width: 50%;

background-color:red;

}

li{

font-size: 2em;

}

</style>

<body>

<nav>

<ul>

<li>Home</li>

<li>About</li>

<li>Contact</li>

</ul>

</nav>

<div>

<div>Hello World</div>

<div> Hello World</div>

<span> Hello World</span>

<span> Hello World</span>

<span> Hello World</span>

</div>

</body>

</html>
```


# Divs and Spans
Using divs and spans can help with the selection of elements

``` html
<!DOCTYPE html>

<html lang="en">

  

<head>

<title> title </title>

<style>

.ingredient {

color: red;

}

  

span.ingredient {

background: yellow;

}

  

li span.ingredient{

background:green

}

</style>

  

<body>

  

<div>

<div>Hello World</div>

<div class="ingredient"> Hello World</div>

<span> Hello World</span>

<span class="ingredient"> Hello World</span>

<ul>

<li>

<span class="ingredient"> Hello World</span>

</li>

</ul>

</div>

</body>

  

</html>
```


# Styling text
```html
<!DOCTYPE html>

<html lang="en">

  

<head>

<title> title </title>

<style>

li{

color: red;

}

.textRight{

text-align: right;

text-decoration: overline;

}

.textLeft{

text-align: left;

text-decoration: line-through;

}

.textCenter{

text-align: center;

text-transform: uppercase;

}

.textJustify{

text-align: justify;

}

a{

text-decoration: none;

/*gets rid of nhyperlinks*/

}

.myClass{

text-indent: 40px;

letter-spacing: 5px;

line-height: 2;

}

.class2{

direction: rtl;

word-spacing: 20px;

}

.class3{

text-shadow: -5px 10px purple;

}

  

</style>

  

<body>

  

<ul>

<li class="textRight">Lorem ipsum dolor sit amet consectetuer.</li>

<li class="textLeft">Aenean commodo ligula eget dolor.</li>

<li class="textCenter">Aenean massa cum sociis natoque penatibus.</li>

</ul>

  
  

<h1 class="class3">Lorem ipsum dolor sit amet consectetuer adipiscing

elit</h1>

<p class="textJustify">Lorem ipsum dolor sit amet, consectetuer adipiscing

elit. Aenean commodo ligula eget dolor. Aenean massa

<strong>strong</strong>. Cum sociis natoque penatibus

et magnis dis parturient montes, nascetur ridiculus

mus. Donec quam felis, ultricies nec, pellentesque

eu, pretium quis, sem. Nulla consequat massa quis

enim. Donec pede justo, fringilla vel, aliquet nec,

vulputate eget, arcu. In enim justo, rhoncus ut,

imperdiet a, venenatis vitae, justo. Nullam dictum

felis eu pede <a class="external ext" href="#">link</a>

mollis pretium. Integer tincidunt. Cras dapibus.

Vivamus elementum semper nisi. Aenean vulputate

eleifend tellus. Aenean leo ligula, porttitor eu,

consequat vitae, eleifend ac, enim. Aliquam lorem ante,

dapibus in, viverra quis, feugiat a, tellus. Phasellus

viverra nulla ut metus varius laoreet. Quisque rutrum.

Aenean imperdiet. Etiam ultricies nisi vel augue.

Curabitur ullamcorper ultricies nisi.</p>

<h1>Lorem ipsum dolor sit amet consectetuer adipiscing

elit</h1>

<h2 class="class2">Aenean commodo ligula eget dolor aenean massa</h2>

<p class="myClass">Lorem ipsum dolor sit amet, consectetuer adipiscing

elit. Aenean commodo ligula eget dolor. Aenean massa.

Cum sociis natoque penatibus et magnis dis parturient

montes, nascetur ridiculus mus. Donec quam felis,

ultricies nec, pellentesque eu, pretium quis, sem.</p>

</body>

  

</html>
```


# Font family

``` html
<!DOCTYPE html>

<html lang="en">

  

<head>

<title> title </title>

<style>

.myClass{

color: red;

font-family: fantasy;

}

.class2{

color: blue;

font-family: cursive;

}

.class3{

color: green;

font-weight: bold;

}

  

</style>

  

<body>

  

<ul>

<li class="textRight">Lorem ipsum dolor sit amet consectetuer.</li>

<li class="textLeft">Aenean commodo ligula eget dolor.</li>

<li class="textCenter">Aenean massa cum sociis natoque penatibus.</li>

</ul>

  
  

<h1 class="class3">Lorem ipsum dolor sit amet consectetuer adipiscing

elit</h1>

<p class="textJustify">Lorem ipsum dolor sit amet, consectetuer adipiscing

elit. Aenean commodo ligula eget dolor. Aenean massa

<strong>strong</strong>. Cum sociis natoque penatibus

et magnis dis parturient montes, nascetur ridiculus

mus. Donec quam felis, ultricies nec, pellentesque

eu, pretium quis, sem. Nulla consequat massa quis

enim. Donec pede justo, fringilla vel, aliquet nec,

vulputate eget, arcu. In enim justo, rhoncus ut,

imperdiet a, venenatis vitae, justo. Nullam dictum

felis eu pede <a class="external ext" href="#">link</a>

mollis pretium. Integer tincidunt. Cras dapibus.

Vivamus elementum semper nisi. Aenean vulputate

eleifend tellus. Aenean leo ligula, porttitor eu,

consequat vitae, eleifend ac, enim. Aliquam lorem ante,

dapibus in, viverra quis, feugiat a, tellus. Phasellus

viverra nulla ut metus varius laoreet. Quisque rutrum.

Aenean imperdiet. Etiam ultricies nisi vel augue.

Curabitur ullamcorper ultricies nisi.</p>

<h1>Lorem ipsum dolor sit amet consectetuer adipiscing

elit</h1>

<h2 class="class2">Aenean commodo ligula eget dolor aenean massa</h2>

<p class="myClass">Lorem ipsum dolor sit amet, consectetuer adipiscing

elit. Aenean commodo ligula eget dolor. Aenean massa.

Cum sociis natoque penatibus et magnis dis parturient

montes, nascetur ridiculus mus. Donec quam felis,

ultricies nec, pellentesque eu, pretium quis, sem.</p>

</body>

  

</html>

```



# Google fonts
https://fonts.google.com
```html
<!DOCTYPE html>

<html lang="en">

  

<head>

<title> title </title>

<!-- <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&family=Roboto:wght@100&display=swap" rel="stylesheet"> -->

<style>

@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&family=Roboto:wght@100&display=swap');

.myClass{

font-family:'Courier New', Courier, monospace;

}

.class2{

font-weight: bolder;

}

  

</style>

  

<body>

  

<ul>

<li class="textRight">Lorem ipsum dolor sit amet consectetuer.</li>

<li class="textLeft">Aenean commodo ligula eget dolor.</li>

<li class="textCenter">Aenean massa cum sociis natoque penatibus.</li>

</ul>

  
  

<h1 class="class3">Lorem ipsum dolor sit amet consectetuer adipiscing

elit</h1>

<p class="textJustify">Lorem ipsum dolor sit amet, consectetuer adipiscing

elit. Aenean commodo ligula eget dolor. Aenean massa

<strong>strong</strong>. Cum sociis natoque penatibus

et magnis dis parturient montes, nascetur ridiculus

mus. Donec quam felis, ultricies nec, pellentesque

eu, pretium quis, sem. Nulla consequat massa quis

enim. Donec pede justo, fringilla vel, aliquet nec,

vulputate eget, arcu. In enim justo, rhoncus ut,

imperdiet a, venenatis vitae, justo. Nullam dictum

felis eu pede <a class="external ext" href="#">link</a>

mollis pretium. Integer tincidunt. Cras dapibus.

Vivamus elementum semper nisi. Aenean vulputate

eleifend tellus. Aenean leo ligula, porttitor eu,

consequat vitae, eleifend ac, enim. Aliquam lorem ante,

dapibus in, viverra quis, feugiat a, tellus. Phasellus

viverra nulla ut metus varius laoreet. Quisque rutrum.

Aenean imperdiet. Etiam ultricies nisi vel augue.

Curabitur ullamcorper ultricies nisi.</p>

<h1>Lorem ipsum dolor sit amet consectetuer adipiscing

elit</h1>

<h2 class="class2">Aenean commodo ligula eget dolor aenean massa</h2>

<p class="myClass">Lorem ipsum dolor sit amet, consectetuer adipiscing

elit. Aenean commodo ligula eget dolor. Aenean massa.

Cum sociis natoque penatibus et magnis dis parturient

montes, nascetur ridiculus mus. Donec quam felis,

ultricies nec, pellentesque eu, pretium quis, sem.</p>

</body>

  

</html>
```




# CSS floats images

*float*: The CSS float property **controls the positioning and formatting of content on the page**

``` html
<!DOCTYPE html>

<html lang="en">

  

<head>

<title> title </title>

<style>

img{

max-width:100%;

float: right;

}

</style>

  

<body>

  

<ul>

<li class="textRight">Lorem ipsum dolor sit amet consectetuer.</li>

<li class="textLeft">Aenean commodo ligula eget dolor.</li>

<li class="textCenter">Aenean massa cum sociis natoque penatibus.</li>

</ul>

  

<h1 class="class3">Lorem ipsum dolor sit amet consectetuer adipiscing

elit</h1>

<p class="textJustify">Lorem ipsum dolor sit amet, consectetuer adipiscing

elit. Aenean commodo ligula eget dolor. Aenean massa

<strong>strong</strong>. Cum sociis natoque penatibus

et magnis dis parturient montes, nascetur ridiculus

mus. Donec quam felis, ultricies nec, pellentesque

eu, pretium quis, sem. Nulla consequat massa quis

enim. Donec pede justo, fringilla vel, aliquet nec,

vulputate eget, arcu. In enim justo, rhoncus ut,

imperdiet a, venenatis vitae, justo. Nullam dictum

felis eu pede <a class="external ext" href="#">link</a>

mollis pretium. <img src="https://placekitten.com/200/350"> Integer tincidunt. Cras dapibus.

Vivamus elementum semper nisi. Aenean vulputate

eleifend tellus. Aenean leo ligula, porttitor eu,

consequat vitae, eleifend ac, enim. Aliquam lorem ante,

dapibus in, viverra quis, feugiat a, tellus. Phasellus

viverra nulla ut metus varius laoreet. Quisque rutrum.

Aenean imperdiet. Etiam ultricies nisi vel augue.

Curabitur ullamcorper ultricies nisi.</p>

<h1>Lorem ipsum dolor sit amet consectetuer adipiscing

elit</h1>

<h2 class="class2">Aenean commodo ligula eget dolor aenean massa</h2>

<p class="myClass">Lorem ipsum dolor sit amet, consectetuer adipiscing

elit. Aenean commodo ligula eget dolor. Aenean massa.

Cum sociis natoque penatibus et magnis dis parturient

montes, nascetur ridiculus mus. Donec quam felis,

ultricies nec, pellentesque eu, pretium quis, sem.</p>

</body>

</html>
```



# CSS float elements

``` html
<!DOCTYPE html>

<html>

  

<head>

<title>Example 11</title>

<style>

.container div{

border: 1px solid blue;

width: 100px;

height: 70px;

float: left;

}

.box4{

border: 1px solid red;

width: 150px;

height: 100px;

clear: both;

}

</style>

</head>

  

<body>

<section class=" container">

<div class="box1 "> Example 1 </div>

<div class="box2 "> Example 2 </div>

<div class="box3"> Example 3 </div>

</section>

<div class="box4 "> Example 4 </div>

<div class="box5 "> Example 5 </div>

<div class="box6 "> Example 6 </div>

</body>

  

</html>
```


# BOX model

![[Pasted image 20231223120826.png]]


```html
<!DOCTYPE html>

<html>

  

<head>

<title>title</title>

<style>

.container{

padding: 5px 10px 100px 20px;

border: 10px solid black;

border-bottom: 20px dotted red;

margin: 30px;

}

</style>

</head>

  

<body>

<section class=" container">

<div class="box1 "> Example 1 </div>

<div class="box2 "> Example 2 </div>

<div class="box3"> Example 3 </div>

</section>

<div class="box4 "> Example 4 </div>

<div class="box5 "> Example 5 </div>

<div class="box6 "> Example 6 </div>

</body>

  

</html>
```




# Exercise 3
``` html
<!DOCTYPE html>

<html>

  

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<title> title </title>

<link rel="stylesheet" type="text/css" href="samplestyle.css">

</head>

  

<body>

<header>

<div class="logo">My Company website.</div>

<nav>

<ul>

<li>Home</li>

<li>About</li>

<li>Contact</li>

</ul>

</nav>

</header>

<section>

<h2>Page Title</h2>

<p class="highlight">First paragraph <a href="http://www.google.com">Google</a></p>

<p class="bigText">second paragraph</p>

</section>

<section>

<h3>Section Heading</h3>

<p class="oneText">First <span class="highlight">paragraph</span></p>

<p class="twoText">second paragraph<img src="https://via.placeholder.com/250x250"></p>

</section>

<section>

<h3>Section Heading</h3>

<p> Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat

<a href="https://placeholder.com"><img src="https://via.placeholder.com/250x250"></a>nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum</p>

</section>

<footer>

<p>My company footer</p>

</footer>

</body>

  

</html>
```


``` css
@import url('https://fonts.googleapis.com/css?family=Mali');

  

body{

font-family: 'Mali', cursive;

background-color:#3C3176;

}

h2{

color: #10073B;

}

section{

background: #867DB0;

margin: 5px 0px;

padding: 5px;

min-height: 300px;

border: 3px dotted white;

}

  

.logo{

color: white;

text-align: center;

font-size: 1.5em;

font-family: fantasy;

}

  

header{

background-color: black;

}

  

li{

list-style: none;

display: inline-block;

background-color: #231858;

color: white;

width: 70px;

padding: 5px 20px;

margin: 5px;

text-align: center;

}

img{

max-width: 150px;

float: right;

}

  

footer{

background-color: darkgray;

color: white;

text-align: center;

padding: 30px;

}
```



# CSS outline
``` html
<!DOCTYPE html>

<html>

<head>

<title>Outline</title>

<style>

.test1{

outline-style: dashed;

outline-color: red;

outline-width: thick;

border: 5px solid blue;

margin: 1px;

}

.test2{

outline-style: groove;

border: 5px dotted yellow;

  

}

</style>

</head>

<body>

<section class="container">

<div class="test1 "> Example 1 </div>

<div class="test2 "> Example 2 </div>

<div class="test3"> Example 3 </div>

</section>

<div class="test4 "> Example 4 </div>

<div class="test5 "> Example 5 </div>

<div class="test6 "> Example 6 </div>

<div class="test7 "> Example 7 </div>

<div class="test8 "> Example 8 </div>

</body>

</html>
```



# CSS positioning

- static
- relative
- absolute
- sticky

```html
<!DOCTYPE html>

<html>

<head>

<title>Outline</title>

<style>

div{

border: 1px solid blue;

width: 300px;

height: 300px;

}

.container{

position: absolute;

left: 500px;

top: 300px;

}

.test1{

position: absolute;

background-color: red;

left: 100px;

top: 100px;

}

.test4{

position: fixed;

background-color: blue;

left: 50px;

top: 50px;

}

.test5{

background-color: green;

position: relative;

left: 100px;

top: 100px;

}

</style>

</head>

<body>

<section class="container">

<div class="test1 "> Example 1 </div>

<div class="test2 "> Example 2 </div>

<div class="test3"> Example 3 </div>

</section>

<div class="test4 "> Example 4 </div>

<div class="test5 "> Example 5 </div>

<div class="test6 "> Example 6 </div>

<div class="test7 "> Example 7 </div>

<div class="test8 "> Example 8 </div>

</body>

</html>
```




# Exercise 4

``` html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<title> CSS Exercise 4 </title>

<style>

img{

width: 30%;

float: left;

margin: 1.66%;

}

</style>

</head>

<body>

<section> <img src="https://via.placeholder.com/250x250"> <img src="https://via.placeholder.com/250x250"> <img src="https://via.placeholder.com/250x250"> <img src="https://via.placeholder.com/250x250"> <img src="https://via.placeholder.com/250x250"> <img src="https://via.placeholder.com/250x250"> <img src="https://via.placeholder.com/250x250"> <img src="https://via.placeholder.com/250x250"> <img src="https://via.placeholder.com/250x250"> </section>

</body>

</html>
```


# CSS for hyperlinks
- a:link
- a:visited
- a:hover
- a:active

``` html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<title> title </title>

<style>

a{

text-decoration: none;

}

a:link{

color:red;

}

a:visited{

color:green;

}

a:hover{

color:pink;

}

a:active{

color:aqua;

}

div:hover{

background-color: yellow;

}

</style>

</head>

<body>

<ul>

<li><a href="#">Home</a></li>

<li><a href="#1">Services</a></li>

<li><a href="#2">About</a></li>

<li><a href="#3">Contact</a></li>

</ul>

<section class="container">

<div class="test1 "> Example 1 </div>

<div class="test2 "> Example 2 </div>

<div class="test3"> Example 3 </div>

</section>

<div class="test4 "> Example 4 </div>

<div class="test5 "> Example 5 </div>

<div class="test6 "> Example 6 </div>

<div class="test7 "> Example 7 </div>

<div class="test8 "> Example 8 </div>

</body>

</html>
```



# CSS pseudo classes

```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<title> title </title>

<style>

a{

text-decoration: none;

}

a:link{

color:red;

}

a:visited{

color:green;

}

a:hover{

color:pink;

}

a:active{

color:aqua;

}

div:hover{

background-color: yellow;

font-size: 2em;

}

/* .container div:first-child{

background: purple;

} */

div:nth-child(odd){

background:yellow;

}

</style>

</head>

<body>

<ul>

<li><a href="#">Home</a></li>

<li><a href="#1">Services</a></li>

<li><a href="#2">About</a></li>

<li><a href="#3">Contact</a></li>

</ul>

<section class="container">

<div class="test1 "> Example 1 </div>

<div class="test2 "> Example 2 </div>

<div class="test3"> Example 3 </div>

</section>

<div class="test4 "> Example 4 </div>

<div class="test5 "> Example 5 </div>

<div class="test6 "> Example 6 </div>

<div class="test7 "> Example 7 </div>

<div class="test8 "> Example 8 </div>

</body>

</html>
```


# CSS and tables
``` html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<title> title </title>

<style>

table{

width: 300px;

}

th{

background:red;

color: white;

}

th, td{

text-align: center;

padding: 5px;

border: 1px solid #ddd;

}

tr:nth-child(odd){

background-color: #000;

color:#fff;

}

tr:nth-child(even){

background-color:#bbb;

color:#fff;

}

</style>

</head>

<body>

<ul>

<li><a href="#">Home</a></li>

<li><a href="#1">Services</a></li>

<li><a href="#2">About</a></li>

<li><a href="#3">Contact</a></li>

</ul>

<table>

<tr>

<th>First</th>

<th>Last</th>

<th>Age</th>

</tr>

<tr>

<td>Laurence</td>

<td>Svekis</td>

<td>40</td>

</tr>

<tr>

<td>John</td>

<td>Smith</td>

<td>50</td>

</tr>

<tr>

<td>Jane</td>

<td>Johnson</td>

<td>33</td>

</tr>

<tr>

<td>Mike</td>

<td>Jonnes</td>

<td>25</td>

</tr>

</body>

</html>
```


# CSS Overflow and maxWidth

``` html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<title> title </title>

<style>

textarea{

border: 1px solid #888;

overflow: hidden;

}

</style>

</head>

<body>

<textarea>Hello World, just some boring text about nothing at all.</textarea>

<table>

<tr>

<th>First</th>

<th>Last</th>

<th>Age</th>

</tr>

<tr>

<td>Laurence</td>

<td>Svekis</td>

<td>40</td>

</tr>

<tr>

<td>John</td>

<td>Smith</td>

<td>50</td>

</tr>

<tr>

<td>Jane</td>

<td>Johnson</td>

<td>33</td>

</tr>

<tr>

<td>Mike</td>

<td>Jonnes</td>

<td>25</td>

</tr>

</body>

</html>
```




# Align elements
``` html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title> title </title>
    <style>
        ul{
            border:1px solid #ddd;
            width:300px;
            background-color: red;
            margin-left: auto;
            margin-right: auto;
            /* margin: auto; */
        }
        p{
            border: 1px solid red;
            text-align: center;
            width: 300px;
            margin-left: auto;
        }
        .test1{
            border: 1px solid blue;
            position: absolute;
            background: green;
            left: 300px;
            width: 100px;
            top:100px;
        }
        .test2{
            border: 1px solid purple;
            float: right;
            width: 200px;
        }
        .test3{
            border: 1px solid purple;
            float: left;
            width: 200px;
        }
        
    </style>
</head>

<body>
    <div id="wrapper">
        <header>
            <div id="info"> <img src="https://via.placeholder.com/50x50" alt="logo" id="logo" />
                <h1>Example 1</h1>
                <h2>My Website</h2> </div>
            <nav>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Services</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </nav>
        </header>
        <div id="banner">
            <div id="bannerText"> My Banner </div>
        </div>
        <section>
            <article>
                <h1>Page Title</h1>
                <p>Hello World</p>
                <div>
                    <h2>My Work</h2>
                    <p><img src="https://via.placeholder.com/250x150/ffffff/000000" alt="Picture"><img src="https://via.placeholder.com/250x150/000fff/000000" alt="Picture"><img src="https://via.placeholder.com/250x150/ff0000/000000" alt="Picture"><img src="https://via.placeholder.com/250x150/00ff00/000000" alt="Picture"></p>
                </div>
            </article>
            <aside>
                <h2>More information</h2>
                <p><img src="https://via.placeholder.com/150x80/ffff00/000000?text=Hello World" alt="Hello World" /></p>
                <p>blah blah blah</p>
               
            </aside>
            <p class="test1">test1</p>
            <p class="test2">test2</p>
            <p class="test3">test3</p>
        </section>
        <footer>
            <div >
                <h3>About</h3>
                <p>Address</p>
            </div>
            <div>
                <h3>My Details</h3>
                <p>
                    (c)copyright 
                </p>
            </div>
            <div>
                <h3>My Website</h3>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
                <ul>
                    <li><a href="#">Products</a></li>
                    <li><a href="#">About</a></li>
                </ul>
            </div>
        </footer>
    </div>
</body>

</html>
```


