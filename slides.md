title: A brief history of Single Page Applications
output: index.html
theme: theme
controls: false
logo: theme/logo.png
style: style.css

-- centered

# A brief history of Single Page Applications

-- centered

## 2006: jQuery - New Wave JavaScript

### Used today by ~80% of the top million websites

<a href="http://web.archive.org/web/20090214090118/http://digg.com/programming/jQuery_-_New_Wave_Javascript"><img src="img/digg-comments.png" style="width: 70%;" alt="Framework Timeline"></a>

-- centered images

## 2000 - 2007: "Web 2.0"

JavaScript helper libraries:

[![Mootools](img/mootools.png)](http://mootools.net/)
[![PrototypeJS](img/prototype.jpg)](http://prototypejs.org/)
[![script.aculo.us](img/scriptaculous.png)](https://script.aculo.us/)

Widget libraries:

[![YUI](img/yui.png)](http://yuilibrary.com/)
[![ExtJS](img/extjs.jpg)](https://www.sencha.com/products/extjs/)
[![Dojo](img/dojo.png)](https://dojotoolkit.org/)

-- centered

## 2007 - Now: JavaScript application frameworks

<img src="img/framework-timeline.png" style="width: 70%;" alt="Framework Timeline">

-- centered images

# ![DoneJS](img/donejs-logo-white.svg)

[![CanJS](img/can.png)](https://canjs.com/)
[![StealJS](img/steal.png)](https://stealjs.com/)
[![FuncUnit](img/funcunit.png)](https://funcunit.com/)
[![DocumentJS](img/docjs.png)](https://funcunit.com/)
[![Testee](img/testee.png)](https://github.com/bitovi/testee)

-- color blue hero

## Did we learn anything?

- The good and bad of owning the stack
- Long-term backwards compatibility is hard
- Evolving frameworks eventually turn into a collection of libraries
- Old ideas don't die
  - Functional Programming (LISP, 1960s) -> React, RxJS, ImmutableJS
  - SGML (ISO, 1986) -> HTML5
  - Flash MXML (Adobe, 2000) -> Angular, Vue.js
  - EJS (JavaScriptMVC, 2007) -> JSX

--

## A JavaScript project checklist

A checklist of things we found help guide the development of a JavaScript software project:

- The number of steps required for success is too complex for memory
- Learn from other's experience
- Force yourself to remember the "not so fun" stuff
- Guide awkward but important conversations

- [bitovi.github.io/checklist](http://bitovi.github.io/checklist/)

-- dark-grey hero centered

## A Bitovi Case Study

After filling out the checklist in hindsight for all of our previous projects, we calculated influence factors and recorded the correlation to project success for each category.

<br><br>

#### We defined success as on time and budget

[blog.bitovi.com/why-checklist](http://blog.bitovi.com/why-checklist/)

--

<h2 style="margin: 0 2em;"><em>"The major surprise in our data was that development factors are not nearly as meaningful in predicting success as design and management factors."</em></h2>

--

## Case Study Results

* Development __.20 ~ .28__
  * code reviews
  * tests, CI, documentation
* Design __.44 ~ .45__
  * user testing
  * design documentation
* Management __.45 ~ .48__
  * vision, goals and strategy
  * yearly trainings
  * release < 6 months

--

# Best practises

-- centered

## Modlets

<h1 style="height: 85%; vertical-align: center;">
  <img src="img/folders.png" alt="Folders" style="display: inline-block; height: 100%;" />
  VS
  <img src="img/modlets.png" alt="Modlets" style="display: inline-block; height: 100%;" />
</h1>

--

## State based routing

Map parts of the route to application state properties (and vice versa).

```javascript
const appState = {
  page: 'home',
  postId: null
};

route('/:page');
route('/:page/:postId', { page: 'posts' });

route.url({ page: 'posts', postId: 10 }); // /posts/10
route.url({ page: 'user', section: 'account' }); // /user?section=account
```

--

## Functional testing with FuncUnit

[![FuncUnit](img/funcunit.png)](http://funcunit.com)

A functional testing library built on top of __jQuery__ and runs on __QUnit__, __Jasmine__ or __Mocha__:

- Write functional tests in your testing library of choice
- Use jQuery syntax to emulate user input

--

## __Testing a [TodoMVC](http://todomvc.com) app__

```javascript
test('TodoMVC app', function() {
  F('#new-todo').click().type('Do some nerdy stuff\r');
  F('#todo-list li').size(1, 'Got one Todo');
  F('#todo-list li:first label')
    .html('Do some nerdy stuff', 'Todo has correct text');
  F('#todo-count').html(/<strong>1<\/strong>(.*)item(.*)left/,
    'Todo count text is correct');
});
```

Automate it with any test QUnit, Jasmine or Mocha test runner ([example page](http://funcunit.com/site/examples/todo_qunit.html)).

--

## Two more things

--

## Services

-- presenter

![David Luecke](http://gravatar.com/avatar/a14850281f19396480bdba4aab2d52ef?s=200)

## David Luecke

* [<i class="fa fa-github"></i> daffl](https://github.com/daffl)
* [<i class="fa fa-twitter"></i> @daffl](http://twitter.com/daffl)

[daffl.github.io/seattlejs](https://daffl.github.io/seattlejs)