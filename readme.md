# WDI7 Cumulative Quiz

## Instructions

1. Fork this repo.
- Clone your fork.
- Fill in your answers by writing the appropriate area, or placing an 'x' in the square brackets for multiple-choice questions.
- Add/Commit/Push your changes to Github.
- Open a pull request.

## Question 1

You've written the following HTML. When you look at it in your browser, it's just blank! Why?

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Quiz
  </head>
  <body>
    <h1>What a great site.</h1>
  </body>
</html>
```

> Because the title tag is not closed. Need </title> on line 19 or 20.

## Question 2

What's the purpose of the `alt` attribute on image tags?

> If the picture does not load or is broken, the alt tag provides a description of the photo. Also used to help with accessibility.

## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```

> Selecting theBody like this is returning an array, instead of the actual body property. i would fix this like:
var theBody = document.querySelectorAll("body");
theBody[0].style.backgroundColor = "red";

## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

> red should not be in quotation marks, and there should not be an equals sign. Fixed version:
body{
  background-color: red;
}

## Question 5

**The scenario:** You're starting a new app. You create a local repo and a repo on Github, create a readme file, and put it on Github. Then you run into Juan, who's already done a lot of the work you were planning to do. You want to pull his code down and include it in your repo, and put your combined code up on your Github repo.

All the steps for one way of doing the above have been written below, but in the wrong order. Put them in the correct order.

```
$ cd project-repo
$ git init project-repo
$ git remote add origin git@github.com/username/project-repo.git
$ touch README.md
$ git add .
$ git commit -m "initial commit"
$ git push origin master
$ git remote add juan git@github.com/juan/project-repo.git
$ git merge juan/feature
$ git push origin master

```

## Question 6

Your Rails database has two tables. `students` has the columns `id` and `name`, and `sandwiches` has the columns `id`, `type`, and `student_id`.

Use ActiveRecord to create a new `pbj` sandwich and make it belong to the student named Geraldo.

```rb
geraldo = Student.create(name: "Geraldo")
Sandwith.create(type: "pbj", student: geraldo)

```

## Question 7

Using Ruby, instantiate an array called `fruits` that contains `apple`, `banana`, and `orange`.

Then, use an enumerator to print to the console the sentence "I'd like to eat a [fruit]" once for each fruit.

```rb
fruits = ["apple", "banana", "orange"]
fruits.each do |fruit|
  puts = "I would like to eat a #{fruit}!"
end
```

## Question 8

Write one Express route for each of four HTTP methods.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

```js
var express = require("express");
var app = express();

// Your code starts here...
app.get("/", function(req, res){
  res.send("Read");
});

app.post("/", function(req, res){
  res.send("Create");
});

app.put("/", function(req, res){
  res.send("Update");
});

app.delete("/", function(req, res){
  res.send("Destroy");
});
```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

> The bang! makes an app throw and error if the save action is unsuccessful. Without the bang, the app would not throw an error. "Fail early, fail often"

## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js
.ajax({
  url: "http://tunr.com/artists",
  type: "post",
  data: {artist: {name; "Resin Laying Deer Figurine, Gold"}}
  dataType: "json"
  .done(function(response){
    alert("ALL done!")
  }),
  .fail(function(response){
    alert("ajax request uncuccessful")
  });

```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js

function Instructor(name){
  this.name = name;
}
Instructor.prototype.recievePresent = function(gift){
  console.log(this.name + "promptly drops the" + gift + "on the floor.");
}

var andy = new Instructor("andy");
andy.recievePresent("Resin Laying Deer Figurine, Gold");

```

## Question 12

Your Rails app has the following `application.html.erb`. Nothing shows up in your browser on any of your app's pages. Why not?

```erb
<!DOCTYPE html
<html>
<head>
  <title>Quiz</title
  <%= stylesheet_link_tag "application", media: "all", "data-turbolinks-track" => true %>
  <%= javascript_include_tag "application", "data-turbolinks-track" => true %>
  <%= csrf_meta_tags %>
</head>
<body>
  <% yield %>
</body>
</html>
```

> The <!DOCTYPE html> on line 1 is missing a closing tab, the </title> on line 160 is also missing a closing tag. Also the yield on line 171 needs to be <%= yield %> in order for all the html/hbs to actually be printed out on the page.

## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?

> Option B is the most correct way of organizing an Angular class. This option is considered "better" because it separates the logic and views related to a model into its own folder achieving proper separation of concerns. This makes it easier for the developer to see how pieces of code relate to the actual app.

### A:
```
/js
  app.js
  controllers/
    artist_index.js
    artist_show.js
  directives/
    artist_form.js
    song_form.js
  views/
    artist_index.html
    artist_show.html
    artist_form.html
    song_form.html
```

### B:
```
/js
  app.js
  artists/
    index.controller.js
    index.html
    show.controller.js
    show.html
    form.directive.js
    form.html
  songs/
    form.html
    form.directive.html
```

### C:
```
/js
  app.js
  controllers/
    artists_controller.js
  directives/
    songs_directive.js
/html
  artists/
    index.html
    show.html
    form.html
  songs/
    form.html
```

## Question 14

Convert the following ActiveRecord sequence to Mongoose:

```rb
@andy = Instructor.find_by(name: "Andy")
@andy.wishlist_items.create(description: "Resin Laying Deer Figurine, Gold")
```

```js

var andy = Instructor.findOne(name: "Andy")
var deer = new wishListItem({
  description: "Resin Laying Deer Figurine, Gold"
})
deer.save();
andy.wishListItem.push(deer)
andy.save();


```
