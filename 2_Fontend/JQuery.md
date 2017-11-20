# Jquery #

javascript library - simplifies Javascript program

## Syntax ##

```javascript
$(document).ready(function(){
    $(selector).action()
});
```

## Selector ##

CSS selector

    $("p.intro") <p> element with class="intro"
    $("p:first") <p> first <p>
    $("ul li:first") first <li> of first <ul>
    $("ul li:first-child") first <li> element of every <ul>

## Events ##

    $().event(function(){
    });

* click
* dbclick
* mouseenter (mouse pointer)
* mouseleave
* mousedown (press down)
* mouseup
* hover(func1(), func2())
* focus (form get select)
* blur  (form loses focus)

### on() Method ###

```javascript
$("p").on("event handler", function (){});

$("p").on({
    mouseenter: function(){},
    mouseleave: function(){},
    click: function(){}
});
```

## Function ##

### Get and Set for ###

* $(selector).text("set") - Set or return text content
* .html("< b> set < /b>") - Set or return text include html tag
* .val("set") - Set or return the value of **form fields**
* .attr("attri-name") - Set or return attribute value

```Javascript
$("button").click(function(){
    $("#w3s").attr("href", "https://www.w3schools.com/jquery");
});
$("button").click(function(){
    $("#w3s").attr({
        "href" : "https://www.w3schools.com/jquery",
        "title" : "W3Schools jQuery Tutorial"
    });
});
```

* callback

```javascript
$(selector).text(function(){});

$("button").click(function(){
    $("#w3s").attr("href", function(i, origValue){
        return origValue + "/jquery"; 
    });
});
```

### Add and Remove Element to HTML ###

* append("<>text<>") - insert content **at the end**
* prepend("") - insert **at the begin** of the element

```javascript
function appendText() {
    var txt1 = "<p>Text.</p>";               // Create element with HTML
    var txt2 = $("<p></p>").text("Text.");   // Create with jQuery
    var txt3 = document.createElement("p");  // Create with DOM
    txt3.innerHTML = "Text.";
    $("body").append(txt1, txt2, txt3);      // Append the new elements
}
```

* after() - insert after the select element
* before()

```javascript
function afterText() {
    var txt1 = "<b>I </b>";                    // Create element with HTML  
    var txt2 = $("<i></i>").text("love ");     // Create with jQuery
    var txt3 = document.createElement("b");    // Create with DOM
    txt3.innerHTML = "jQuery!";
    $("img").after(txt1, txt2, txt3);          // Insert new elements after <img>
}
```

* remove("selector") - remove select element and child element
* empty() - remoce child element

```javascript
$("p").remove(".test, .demo");
```

### SET and GET CSS ###

* addClass() - add class attributes to one or more elements
* removeClass() - remove on or more attributes
* toggleClass() - toggle between add and remove
* css() - sets and get attribute value

css("propertyname","value");
css({"propertyname":"value","propertyname":"value",...});

* width() - content element
* height()
* innerHeight() - element + padding
* innerWidth()
* outerWidth() - element + padding + border
* outerHeight()
* outerHeight(true) - element + padding + border + margin

$(document).width()
$(window).height();

### Display Effect ###

```javascript
$("element").hide()
```

Hide element

* .hide(speed, callback) - specified the speed of hiding/showing - take "slow" "fast" or millsecond
* .show()
* .toggle(speed, callback) -  switch between hide and show

--------
Fade element

* fadeIn(speed, callback) - fade in hide element "slow" "fast" millsecond
* fadeOut()
* fadeToggle()
* fadeTo(speed, opacity, callback) - fade to given opacity

--------
Slide element

* slideDown(speed, callback)
* slideUp()
* slideToggle()

--------
Add animate, apply CSS in order

* .animate({params}, speed, callback) - CSS properties in camel: padding-left -> paddingLeft

```javascript
$("div").animate({left: '250px',
        opacity: '0.5',
        height: '150px',
        width: '150px'});
```

* multiple animate comes in queue

--------
stop animate before it finished

* .stop(stopAll, goToEnd) - stopAll clear animate queue, default false/ goToEnd whether or not finish the current anumation immdiately, default is false

--------
CallBack used to execute after effect (正常使用的话可能会在效果完成前执行function)

Chaining method or function - like animation

```javascript
$("#p1").css("color", "red")
  .slideUp(2000)
  .slideDown(2000);
```

## Traversing ##

* $(selector).parent(); - direct parent
* $(selector).parents(); - all parents
* .parentsUntil(selector); - parents between two selector (not include selector)\

--------

* children(selector/ filter) - all direct children
* find(selector/ filter) - all desecendent of select element