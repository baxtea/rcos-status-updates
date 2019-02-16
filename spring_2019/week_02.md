## Last Week's Accomplishments

Wrote a broken selection properties popup
- Only for title and position properties
- Shows up when things are selected, as intended
- Toggles modules according to the properties of selected (i.e. if you select something)
    - At least, I have the framework for it. Since I only have name and position components, they never disable because all elements have those properties.
    - Might need to refactor the compoonent system slightly to make this clean
- Doesn't position itself correctly
    - Especially glaring when dragging components, it doesn't move with the selection(s).
    - Also I'm taking positions in canvas space and using them to position DOM elements without any changes. Can result in elements positioned offscreen or wildly far away from the selections
- Unable to properly push updates from the modules when they are changed
    - HTMLInputElement.value isn't working for some reason? Always gives undefined
  - Perhaps it's a consequence of using oninput? Not sure...

## This Week's Plan

- Don't be late with my next progress post 😅
- Proceed with porting the selection properties popup
- At least fix the positioning of the popup
    - Perhaps porting the DOM approach isn't smart now that the rest of the project is on an HTML5 canvas
-  Want to do module enabling/disabling a different way that JS-style property checks but not sure how -- ES5 descriptor reflection metadata might work
    - Can't do interfaces because TS interfaces are duck-typed and class information is not stored
    - Can't do abstract classes because classes can only have one parent and I would need more than that
    - I'm thinking something like `@pull("position")` and `@push("position")` decorators on `getPos` and `setPos`, respectively
    - Maybe I can notate classes instead of functions? That would work around duck-typed interfaces...
    - Would still need some clever data structures in the reflection to avoid the sort of gross type-casting hell I'm in now

## Anything Blocking?

- Uncertainty as to whether I should continue with HTML elements or begin porting it to the canvas
- Frustration with HTMLInputElement