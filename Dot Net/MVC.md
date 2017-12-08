# MVC #

Model - View - Controller is software architecture pattern

## Why ##

Code reuse & separation of concerns

* Model - are the parts of the application that implement the logic for the application's data domain. retrive and store model state in a database
  * describe data
  * rules to change data
  * Data Access Layer

* View - are components that display the application'user interface

* Controller - handler user interaction, work with model and select a view to render that display UI
  * hold the logic
  * handle the communication with user
  * handle overall application flow
  * application - specific logic

## Reason not use webform ##

* limited control over HTML
* mixing presentation and logic
* hard to test
* Complex page life cycle
* hard to integrate with other libraries

## ASP.NET MVC ##

* on top of asp.net
* SEO - (search engine operation) User friendly URL - extensible routing system
* Adopt REST concepts
* provide convention and Guidance
* separation of concern
* tight control over HTML
* Design to be testable
* better integration with 3rd party libraries

## MVC routing ##

controller + action + parameters

First match (from top to bottom)

```C#
routes.MapRoute(
    name: "",
    url: "{year}/{month}/{day}",
    defaults: new { year = "", month ="" },
    constraints: new { year = "regexp"}
)
```

access route data

* RouteData.Values["controller"]

## MVC Controller ##

inherit controller class - access Request and HttpContext

Non-Action Method - void type method

Action Method

* Controller defines action methods
* Action Method are dependent on Routing
* Action method typically have one-to-on mapping with user interaction
* Public/ Non-static/ No return value
* return ActionResult

ActionResult

* View Result - View (as web page)
* Partical View Result - Partical View(define a section of view)
* Redirect Result - Redirect(Redirects to another action View url)
* Redirect to Route - Redirect to action
* Json Result
* Content - user-define content
* javascript
* File
* Empty

Action Parameters

* Routing engine can pass parameters(Users/{username})
* URL query string(User?username=xxx)
* Http post data

```C#
public ActionResult funtion(string username){}
```

Action Selector

* [ActionName("replace the action name in routing")]
* [HttpPost/Get/Delete/Options] AcceptVerbs
* [NonAction]
* [RequireHttps]
* [ChildActionOnly] prevent being called directly

## MVC View ##

* Html templates of application
* Master pages (layout views)
* other view can be render in view (partical views)

View Engine

* Aspx .aspx
* RAZOR .cshtml
* spark

Razor

* add code @
* enclosed in braces @ { code }
* can use variable
* @function to add function
* @inherit to specify base class

## Pass Data ##

Controller to View

* View Data
  * ViewData["message"] = new {}
  * @ViewData["message"]
  * require typecasting && check null value
* View Bag
  * ViewBag.Message =
  * @ViewBag.Message
  * available for the current request
  * redirection will set to null
* @Model
  * return View(model)
  * @model modeldatatype
  * strong type better compile time
* Temp Data
  * passdata to another action
  * TempData["data"] + RedirectToAction()
  * require typecasting

View to Controller

* Form Collection
  * ActionResult function(string collection)
  * collection["StudentFirstName"]
* throught parameters
  * < input type="text" name="FirstName" value="" />
  * ActionResult function(string FirstName)
* Request
  * Routing engine can pass parameters(Users/{username})
  * URL query string(User?username=xxx)
  * Http post data
* strong typed model binding

## Action Filters ##

are custom attributes that provide a declarative means to add preaction and postaction behaviour to controller action methods

* pre and post processing logic
* applied to actions and to controllers
* Global filter can be registered in globalfilters

Types of filters

* authorization filter
* Action filter - action
* result filter - actionresult
* exception filter

Custom Action Filter

* inherit ActionFilterAttribute
* override
  * onactionexecuting
  * onactionexecuted
  * onresultexecuting
  * onresultexecuted

Layout - @RenderBody()

Section - may render auywhere in the layout page

    @section Name {} define section
    @RenderSection("Name")

## View Helpers ##

View inherits WebViewPage, helper is a method that returns a string

    @using (Html.BeginForm())
    {
      @Html.HelperNameFor(model => )
      strong-type Htmlhelper better compile-time checking
    }

    Custom Helper

```C#
public static TagBuilder Imag(this HtmlHelper helper, string imageurl, string alt)
    {
      TagBuilder imageTag = new TagBuilder("img");
      imageTag.MergeAttribute("src", imageUrl);
      return imageTag;
    }
```

Partial Views - render portions of a page (reuse pieces of view)

    Partial()
    RenderPartial()
    Action()

Scaffolding - auto generate the view and Controller

## ViewModel ##

ViewModel is a pattern that allow to have multiple models as single class it contains properties need to be used in view

## Session TempData Cache ##

Session - HttpContext.Session[""] / store info in memory of application, client focus

TempData - TempData[""] /used like dictionary, last current and next request

Cache - HttpContext.Cache[""] /save global data into Cache, not per client