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

