# Prefresh

- [core](https://github.com/JoviDeCroock/prefresh/tree/main/packages/core)
- [CRA with prefresh](https://github.com/jeremy-coleman/prefresh-cra)
- [gatsby](https://www.gatsbyjs.org/packages/gatsby-plugin-preact/)
- [next](https://github.com/JoviDeCroock/prefresh/tree/main/packages/next)
- [nollup](https://github.com/JoviDeCroock/prefresh/tree/main/packages/nollup)
- [preact-cli (--refresh)](https://github.com/preactjs/preact-cli#preact-watch)
- [snowpack](https://github.com/JoviDeCroock/prefresh/tree/main/packages/snowpack)
- [utils](https://github.com/JoviDeCroock/prefresh/tree/main/packages/utils)
- [vite](https://github.com/JoviDeCroock/prefresh/tree/main/packages/vite)
- [webpack](https://github.com/JoviDeCroock/prefresh/tree/main/packages/webpack)

## Best practices

### Recognition

We need to be able to recognise your components, this means that components should
start with a capital letter and hook should start with `use` followed by a capital letter.
This allows the Babel plugin to effectively recognise these.

Do note that a component as seen below is not named.

```jsx
export default () => {
  return <p>Want to refresh</p>
}
```

Instead do:

```jsx
const Refresh = () => {
  return <p>Want to refresh</p>
}

export default Refresh;
```

When you are working with HOC's be sure to lift up the `displayName` so we can
recognise it as a component.

### Context

We don't have a mechanism in place to hot reload context, that's why our general advice is to move
these to their own files.
