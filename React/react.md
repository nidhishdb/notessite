## React JS
<img src="https://reactjs.org/logo-og.png" width=300 alt="react logo" style="border-radius:4px">

>When something is important enough, you do it even if the odds are not in your favor - *Elon Musk*
- - - -
  
#### Getting started

You can start a project by running CRA with npx - `sudo npx create-react-app project-name`, by doing this you won't have to install create-react-app globally.
(npx comes with npm 5.2+ and higher)

If you use npm 5.1 or earlier, you can't use `npx`. Instead, install `create-react-app` globally:

`npm install -g create-react-app
`

Now you can run:

`create-react-app my-app`

#### Deployment with CRA
https://create-react-app.dev/docs/deployment/#github-pages-https-pagesgithubcom

#### `<Fragment>`
Too many `<div>` tags clutering your JSX? NO PROBLEM, write semantic JSX with `<Fragment>` (React 16+) - http://blog.jmes.tech/react-fragment-and-semantic-html/ 

When creating methods inside a component use a arrow function, as it sets it's `this` to the component it is in.

#### Lifecycle hooks
https://reactjs.org/docs/react-component.html

#### props.children
 Components that wrap around other components can be accessed through props.children
```js
    <Scroll>
        <Card />
    </Scroll>
```
Here `<Card />` component is passed down as a Prop to `<Scroll>` Component.

#### ErrorBoundaries (React16+) - componentDidCatch():

https://reactjs.org/docs/error-boundaries.html

Error boundaries work like a JavaScript catch {} block, but for components. Only class components can be error boundaries. In practice, most of the time you’ll want to declare an error boundary component once and use it throughout your application.

Note that error boundaries only catch errors in the components below them in the tree. An error boundary can’t catch an error within itself. If an error boundary fails trying to render the error message, the error will propagate to the closest error boundary above it.

