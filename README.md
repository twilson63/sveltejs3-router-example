# Svelte Router Example

This is an example project showcasing how one might use pagejs a framework agnostic client side router for your sveltejs app.

## Usage

```sh
yarn
yarn dev
```

## Description

In order to use a router like pagejs you need a root component that is going to be responsible for handling the routing.

In this route components template, you want to use the `<svelte:component />` tag with the `this` property. This special component allows you to assign a local variable as the component.

Create your `router` using pagejs this is simple:

```js
import page from "page";

page("/", () => (component = Home));
page("/about", () => (component = About));

page.start();
```

Using the local state which is as simple as declaring a local variable, we can modify the state which will trigger a re-render:

```js
let component = Home;
```

And that will give us routing, here is how the full component looks:

```html
<svelte:component this="{component}" />
<script>
  // router
  import page from "page";

  // Routes
  import Home from "./pages/Home.html";
  import About from "./pages/About.html";

  // state
  let component = Home;

  // route handlers
  page("/", () => {
    component = Home;
  });

  page("/about", () => {
    component = About;
  });

  page.start();
</script>
```

## LICENSE

MIT

## Contributing

All pull requests are accepted!
