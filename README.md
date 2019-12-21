# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Introduction to React

This is the repo for day 1 of the React week. This covers components, JSX, virtual DOM, props, multiple props, and nested components.

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Intro to React.js

---

![react-logo](./images/react-white-logo.png)

---

Welcome! This lesson assumes you have some JavaScript knowledge and awareness of the DOM tree. Beyond that, we'll be here to teach you!     

## What is ReactJS?

First, let's think about where you might see a React.js app. Here are two quick and easy examples:

- Facebook
  - Facebook actually built React! It needed web pages that could change quickly based on a user's interaction — your Facebook feed, for example.

- Instagram
  - Instagram's public feed and internal system are entirely built on React.

For an intro to React, watch [this video](https://generalassembly.wistia.com/medias/lr8idjxtx8) (note: right click to open in a new tab!).

The React framework was built to solve one problem: building large applications with data that changes over time.

Before React, re-rendering one thing meant re-rendering everything.
This had negative implications on processing power and ultimately user experience, which at times became glitchy and laggy.

React is "agnostic" to other tools in your front end. This means that React can co-exist with other Javascript frameworks, letting the other frameworks handle the models and controllers and having React sort out the views.


#### Some History

For a quick rundown, React was...
* First used by Facebook in 2011.
* Adopted by Instagram in 2012.
* Made open source in May 2013.

This can be extrapolated to - both Facebook and Instagram are React apps!

To get more hands on and in-depth down the React rabbit hole, let's keep going!


*If you want to get an in-depth taste of what React is all about, [here's an introduction from React.js Conf 2015](https://www.youtube.com/watch?v=KVZ-P-ZI6W4&feature=youtu.be&t=510). (note: right click to open in a new tab!). We'd recommend starting around the 8:35 mark and watching until 16:30. This link is also in the Further Reading page at the end of the React module.*


# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Hello World exercise - We do!


### Learning Objectives
*After this lesson, you will be able to:*
- Build a React app using `create-react-app`
- View `create-react-app` working locally

## Initial Setup

Let's jump right in! We'll create a skeleton React project and walk through it as we go.

An easy way to start React projects is to use a Terminal program called `create-react-app`. This excellent tool, created by Facebook, will help you set up a bare-bones React app instantly. We can simply install the package and start coding.

Let's use `npm` to install it globally so we'll always have it available in our Terminal. Run:

```sh
$ npm i -g create-react-app
```

Once it's installed, create a new directory to store the app you're about to write and `cd` to the folder. Then, use the tool to create a new React app. You'll have to give your new app a name; we're calling the example app "hello_world", since that'll be our first project.


```sh
$ create-react-app hello_world
```

The tool creates a new directory for your app, so move into it...

```sh
$ cd hello_world
```

Use `npm start` to start a server that will serve your new React application!

```sh
$ npm start
```

> You have now set up a Hello World app that you will continue working on during this lesson's exercises!

After running `$ npm start`, you can view the app at `http://localhost:3000`

> Note: If you ever need to stop the server, you can hit `ctrl-c` in the terminal window.

You'll notice the web page for our app automatically refreshes every time we save a file in the directory. This is an awesome feature of `create-react-app`


You can look in the directory and see the structure that `create-react-app` provides for us. It looks like this:

```sh
├── README.md
├── package.json
├── public
│   ├── favicon.ico
│   └── index.html
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    └── logo.svg
```

Most of the important files are in the `src` directory. Specifically, we'll be using `src/App.js` and `src/index.js`.

---

## Stop / Catch Up / Investigate

Take some time and look at what's been generated. Specifically pay attention to `src/App.js` and `src/index.js`

Make small changes to the code in `src/App.js`, `src/index.js`, and `public/index.html` just to see what happens.

Your basic React app is up and running. Now you're ready to add complexity.

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Components and JSX


### Learning Objectives
*After this lesson, you will be able to:*
- Identify and define React components
- Describe why we use components in React
- Build a React component
- Describe JSX

## Components

The basic unit you'll be working with in ReactJS is a **component**. Components are pieces of our application that we can define once and reuse all over the place.

For an intro to components, watch [this video](https://generalassembly.wistia.com/medias/h64z7lp1ir) (note: right click to open in a new tab!).


If you're used to writing out all of a page's view in a single HTML file, using components is a very different way of approaching web development.

With components, there is more integration and less separation of HTML, CSS, and JavaScript.
- Instead of creating a few large files, you will organize your web app into small, reusable components that encompass their own content, presentation, and behavior.

When using React, building components will be your main front-end task.
- Because they're so encapsulated, components make it easy to reuse your code, test, and separate concerns.

### [F.I.R.S.T. Components](https://addyosmani.com/first/)

A React component is built to expect an input and render a UI with it. More importantly, a well-structured component only receives data specific to its purpose.

This is because React follows a more **functional** approach to programming. For React components under this approach, **the same input will always produce the same output**.

Best practice is that React components follow the **F.I.R.S.T.** guidelines

#### Focused

Components should do one thing and do it well.

#### Independent

Components should increase cohesion and reduce coupling. Behavior in one component should not impact the behavior of another. In other words, components should not rely on one another.

> But they should compliment one another.

#### Reusable

Components should be written in a way that reduces the duplication of code.

#### Small

Ideally, components should be short and condensed.

#### Testable

Because the same input will always produce the same output, components are easily unit testable.

> If you're interested, [Jest](https://facebook.github.io/jest/docs/tutorial-react.html) is a popular testing library for React.

### Identifying Components

Take a look at [CraigsList](https://boston.craigslist.org/search/aap) (note: right click to open in a new tab!).

![Components](images/craigslist.png)

Each listing is a component. How can you identify this?
- Listings look identical in structure, but have different information populating them
- Listings are dynamically generated based on the user's search

<!--- Now, go to [Amtrak.com](https://www.amtrak.com/home) (note: right click to open in a new tab!). We want to look at the listing page, so put in any "From" (for example, New York - Penn Station), any "To" (for example, Boston - South Station), and pick any date. Hit "Find Trains". Now look at the listing page:

![Amtrak](images/amtrak.png) --->

Now, check out this website, Tube Tracker.

![tube tracker](https://i.imgur.com/59nCojL.png)

Scrolling down it, identify the visual "components" the website is comprised of. We suggest drawing this out on paper! So something like this...

![Component diagram](images/wireframe_deconstructed.png)

As you're drawing this out, think about the following questions...

* Where do you see "nested components;" that is, where are there components inside another component? Where do you see just one "layer" instead?
* Are there any components that share the same structure?
* For components that share the same structure, what is different about them?


### So -

What does a component look like? Let's start with a simple "Hello World" example...

#### Code along: A Very Basic Component

In this section, we'll walk through:
* Removing the pre-filled contents of your `hello_world` app.
  - `create-react-app` filled your app with sample content - let's make room for your app!
* Adding your own component definition.
  - You want the app to display the words "Hello World!"
- Going through what we've done in detail!

To start, remove the entire contents of the `src/App.js` file.

Then, add the component definition below.

```js
// bring in React and Component from React

import React, {Component} from 'react';

// define our Hello component
class Hello extends Component {
  // what should the component render?
  render () {
    // make sure to return some UI
    return (
      <h1>Hello World!</h1>
    );
  }
}

export default Hello;
```

Let's break down the things we see here...

##### `import React, {Component} from 'react'`;
This imports React methods and the `Component` class from the React library.

##### `class Hello`
This is the component we're creating. In this example, we are creating a component and calling it "Hello."

##### `extends Component`

We inherit from the `Component` React library class to create our component definitions. Here, we are creating a new `Component` subclass called `Hello`.
- Because it extends (also known as inherits from) `Component`, our `Hello` class gets to reuse code and capabilities from `React.Component`.

##### `render()`
Every component has, at minimum, a `render` method. The `render` method is what renders the component to the screen, so it controls what is displayed for this component. From this function, we return what we want to display.  
- In our case, we are rendering a "Hello World!" heading: `<h1>Hello World!</h1>`.

> Note! That heading tag above looks like it's straight out of HTML, but it's actually a special language called JSX, which you'll see on the next page. For now, know that JSX will act like HTML when it's rendered to the screen.

##### `export default Hello`;
This exposes the `Hello` class to other files.  This means that other files can `import` from the `App.js` file in order to use the `Hello` class. In our case, we'll be importing it into `index.js` by calling an `import` to `App.js`.

When we try to import something from `App.js`, JavaScript will attempt to match a named export.
- Our only named export in `App.js` is `Hello`.

The `default` keyword means that if we try to import anything from this file that the app can't find, JavaScript will automatically revert to importing `Hello` instead.
- Only one default export is allowed per file.

### Check it out!

If you switch to your browser and navigate to http://localhost:3000, you can see your "Hello World!" heading. This app dynamically reloads each time you save, so you can check your changes at any point.


### Wait - What's that HTML doing in my Javascript?

This is currently the contents of our `src/App.js` file:

```js
// bring in React and Component from React

import React, {Component} from 'react';

// define our Hello component
class Hello extends Component {
  // what should the component render?
  render () {
    // make sure to return some UI
    return (
      <h1>Hello World!</h1>
    );
  }
}

export default Hello;
```

Let's talk about the value that the render method returns. It looks an awful lot like an HTML heading, but it's not. We often write out React components in **JSX**.

Wait, what's that? Try it yourself alongside [this video](https://generalassembly.wistia.com/medias/dcps4dqziy) in [this codepen](https://codepen.io/susir/pen/wJPoBw) (note: right click  both links to open in a new tab!)

So, JSX allows us to write code that strongly resembles HTML. It is eventually compiled to lightweight JavaScript objects.

Your `Hello` component's `render` method:
- Currently returns JSX, not HTML.
- The JSX creates a heading with `'Hello World!'`.
- Your component reads this and renders a "Hello World!" heading.

> React can be written without JSX. We won't be doing this, but if you want to learn more, [check out this blog post](http://jamesknelson.com/learn-raw-react-no-jsx-flux-es6-webpack/) (note: open in new tab!).

### Challenge: Greet the day!

- Change your `Hello` component to return multiple lines.
  - Add a line below the "Hello World!" heading that will display `"It is time for tea."` in an `h3`.

> Hint: Remember, the return statement in `render` can only return one DOM element. You can, however, place multiple elements within a parent `div` element.*
