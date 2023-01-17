# Miscellaneous Resources: React

## [Portals](https://reactjs.org/docs/portals.html) (lesser known React API):

- Portals are used to 'teleport' a React component to different part of the real DOM.
- Useful for modal dialogs, hovercards and tooltips, where a child still 'belongs' to a parent, but needs to visually 'break out' (and the parent has `overflow: hidden` or similar).
- Be careful with managing keyboard focus.
- Vue has an equivalent API: [Teleport](https://vuejs.org/guide/built-ins/teleport.html).
