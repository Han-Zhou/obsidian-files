
# Update Html element

functions and commands:
- document
- console.dir(document)
- console.log();

``` html
<!DOCTYPE html>
<html>
 
<head>
    <title>title</title>
</head>
 
<body>
    <h1>JavaScript<h1>
    <button type="button">Click</button>

    <script>
        console.dir(document);
        console.log('hello');
	    
	    
	    
	    
	    document.querySelector('h1').innerHTML="hello world";
    </script>

</body>
 
</html>
```

# JavaScript Code

Comments: //
[comment]: /**/

line breaks and spaces are acceptable


# Variables

Ways to contain data and to store data


# DOM
Document object model;
more documentations online;



# Skills in DOM

## Manipulation 
``` html
<!DOCTYPE html>
<html>

<head>
    <title>JavaScript DOM Course</title>
</head>

<body>
    <h1>Lorem ipsum dolor sit amet consectetuer adipiscinelit</h1>
    <ul>
        <li id="one">Lorem ipsum dolor sit amet consectetuer.</li>
        <li class="highlight">Aenean commodo ligula eget dolor.</li>
        <li>Aenean massa cum sociis natoque penatibus.</li>
    </ul>
    <p class="highlight">Lorem ipsum dolor sit amet, consectetuer adipiscing
        elit. Aenean commodo ligula eget dolor. Aenean massa.
        Cum sociis natoque penatibus et magnis dis parturient
        montes, nascetur ridiculus mus. Donec quam felis,
        ultricies nec, pellentesque eu, pretium quis, sem.</p>
    <ul>
        <li class="highlight">Lorem ipsum dolor sit amet consectetuer.</li>
        <li>Aenean commodo ligula eget dolor.</li>
        <li>Aenean massa cum sociis natoque penatibus.</li>
    </ul>
    <script>
        var el1 = document.querySelector('#one');
        console.dir(el1.innerHTML);
        el1.innerHTML = "Hello World";
        el1.style.color = 'red';
        el1.style.background = 'blue';
        el1.innerText = "TEST";

    </script>
</body>

</html>
```

## Selection
``` html
<!DOCTYPE html>
<html>

<head>
    <title>JavaScript DOM Course</title>
</head>

<body>
    <h1>Lorem ipsum dolor sit amet consectetuer adipiscinelit</h1>
    <ul>
        <li id="one">Lorem ipsum dolor sit amet consectetuer.</li>
        <li class="highlight">Aenean commodo ligula eget dolor.</li>
        <li>Aenean massa cum sociis natoque penatibus.</li>
    </ul>
    <p class="highlight">Lorem ipsum dolor sit amet, consectetuer adipiscing
        elit. Aenean commodo ligula eget dolor. Aenean massa.
        Cum sociis natoque penatibus et magnis dis parturient
        montes, nascetur ridiculus mus. Donec quam felis,
        ultricies nec, pellentesque eu, pretium quis, sem.</p>
    <ul>
        <li class="highlight">Lorem ipsum dolor sit amet consectetuer.</li>
        <li>Aenean commodo ligula eget dolor.</li>
        <li>Aenean massa cum sociis natoque penatibus.</li>
    </ul>

    <script>
        var el1 = document.getElementById('one');
        el1.style.background = "yellow";
        var el2 = document.getElementsByTagName('li');
        console.log(el2);
        var el3 = document.getElementsByClassName('highlight');
        console.log(el3);
        var el4 = document.querySelector('.highlight');
        console.log(el4); //only returns the first element
        var el5 = document.querySelectorAll('.highlight');
        console.log(el5);
        el5[0].style.color = 'yellow';

    </script>
</body>

</html>
```


# Element Test Manipulation

``` html
<!DOCTYPE html>
<html>

<head>
    <title>JavaScript DOM Course</title>
</head>

<body>
    <h1>Lorem ipsum dolor sit amet consectetuer adipiscinelit</h1>
    <ul>
        <li id="one">Lorem ipsum dolor sit amet consectetuer.</li>
        <li class="highlight">Aenean commodo ligula eget dolor.</li>
        <li>Aenean massa cum sociis natoque penatibus.</li>
    </ul>
    <p class="highlight">Lorem ipsum dolor sit amet, consectetuer adipiscing
        elit. Aenean commodo ligula eget dolor. Aenean massa.
        Cum sociis natoque penatibus et magnis dis parturient
        montes, nascetur ridiculus mus. Donec quam felis,
        ultricies nec, pellentesque eu, pretium quis, sem.</p>
    <ul>
        <li class="highlight">Lorem ipsum dolor sit amet consectetuer.</li>
        <li>Aenean commodo ligula eget dolor.</li>
        <li>Aenean massa cum sociis natoque penatibus.</li>
    </ul>

    <script>
        var el1 = document.querySelector('.highlight');
        console.log(el1)

        // innerHTML difference with outerHTML

    </script>
</body>

</html>
```



# Change classes DOM
```html
<!DOCTYPE html>
<html>

<head>
    <title>JavaScript DOM Course</title>
    <style>
        .red{
            background-color: red;
        }
        .test{
            margin: 10px;
            padding: 10px;
            border: 1px solid black;
        }
    </style>
</head>

<body>
    <h1 class="test">Lorem ipsum dolor sit amet consectetuer adipiscinelit</h1>

    <script>
        var el1 = document.querySelector('h1');
        console.dir(el1);
        // el1.className = "red";
        // el1.classList.add('red');
        el1.classList.toggle('red');
    </script>
</body>

</html>
```



# Change Styles DOM

``` html
<!DOCTYPE html>
<html>

<head>
    <title>JavaScript DOM Course</title>
    <style>
        .red{
            background-color: red;
        }
        .test{
            margin: 10px;
            padding: 10px;
            border: 1px solid black;
        }
    </style>
</head>

<body>
    <h1 class="test">Lorem ipsum dolor sit amet consectetuer adipiscinelit</h1>

    <script>
        var el1 = document.getElementsByClassName('test');
        console.log(el1[0]);
        var tempEle = el1[0];
        tempEle.style.backgroundColor = "Green";
        tempEle.style.color = "white";
        tempEle.style.border = "5px dotted purple";
        tempEle.style.fontSize = "40px";
        //tempEle.style.display = "none";
        tempEle.style.display = "block";
        
    </script>
</body>

</html>
```



# Element attribute Manipulation

```html
<!DOCTYPE html>
<html>

<head>
    <title>JavaScript DOM Course</title>
    <style>
        
    </style>
</head>

<body>
    <a href="https://placeholder.com"><img src="https://via.placeholder.com/250/00ffff/000000"></a><br>
    <img src="https://via.placeholder.com/350x150/00ff00/ffffff">

    <script>
        var el1 = document.getElementsByTagName('a');
        console.log(el1[0]);
        var el2 = document.getElementsByTagName('img');
        console.log(el2[1]);
        var temp = el1[0].getAttribute('href');
        el1[0].setAttribute('href', "https://www.google.com");
        var tempImg1 = el2[0].getAttribute('src');
        var tempImg2 = el2[1].getAttribute('src');
        el2[0].setAttribute('src', tempImg2);
        el2[1].setAttribute('src', tempImg1);
    </script>
</body>

</html>
```



# Interactive DOM events

``` html

<!DOCTYPE html>
<html>

<head>
    <title>title</title>
    <style>
        
    </style>
</head>

<body>
    <ul>
        <li>My Item</li>
        <li>Another Item</li>
        <li>Wow Item</li>
        <li>New Color</li>
    </ul>

    <script>
        var ele1 = document.querySelector('ul');
        ele1.addEventListener('click', function(){
            console.log('click');
            ele1.style.backgroundColor = "yellow";
        })
    </script>
</body>

</html>
```



# Select Multiple Elements

``` html
<!DOCTYPE html>
<html>

<head>
    <title>title</title>
    <style>
        .red{
            background-color: red;
        }
    </style>
</head>

<body>
    <ul>
        <li>My Item</li>
        <li>Another Item</li>
        <li>Wow Item</li>
        <li>New Color</li>
    </ul>

    <script>
        var eleList = document.querySelectorAll('li');
        for(var x = 0; x < eleList.length; x++){
            eleList[x].addEventListener('click', function(){
                console.log(this);
                var temp = this.classList.toggle('red');
                console.log(temp);
            })
        }
    </script>
</body>

</html>
```



#  KeyPress Events

``` html
<!DOCTYPE html>
<html>

<head>
    <title>title</title>
    <style>
        .red{
            background-color: red;
        }
    </style>
</head>

<body>
    <ul>
        <li>My Item</li>
        <li>Another Item</li>
        <li>Wow Item</li>
        <li>New Color</li>
    </ul>
    <input type="text" name="newItem"> 

    <script>
        var ele = document.querySelector('input[name="newItem"]');
        ele.addEventListener('keypress', addItem);
        var eleUL = document.querySelector('ul');

        function addItem(event){
            console.log(event);
            if(event.keyCode == 13){
                console.log('sss');
                eleUL.style.backgroundColor = "yellow";
            }
        }

        console.log(ele);

    </script>
</body>

</html>
```


# Mouse events
``` html
<!DOCTYPE html>
<html>

<head>
    <title>title</title>
    <style>
        .red{
            background-color: red;
        }
    </style>
</head>

<body>
    <ul>
        <li>My Item</li>
        <li>Another Item</li>
        <li>Wow Item</li>
        <li>New Color</li>
    </ul>
    <input type="text" name="newItem"> 

    <script>
        var eleList = document.querySelectorAll('li');
        for(var x = 0; x < eleList.length; x++){
            console.log(eleList[x]);
            eleList[x].addEventListener('mouseover', function(){
                this.classList.add('red');
            })
            eleList[x].addEventListener('mouseout', function(){
                this.classList.remove('red');
            })
        }
        // basically recreating css hover effect;
        
    </script>
</body>

</html>
```


# DOM  create your own elements

