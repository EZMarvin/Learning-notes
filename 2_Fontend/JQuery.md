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

## Display Effect ##

```javascript
$("element").hide()
```