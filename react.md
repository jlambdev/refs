# React

## Videos

[10 React Antipatterns to Avoid - Fireship](https://www.youtube.com/watch?v=b0IZo2Aho9Y&ab_channel=Fireship)

-   avoid large components, you can use Glean (VSCode extension) to easily factor our components with props
-   avoid deeply nested components as this can result in unecessary re-renders (child component gets a new memory address, which could lead to unpredictable behaviour)
    -   you can limit child component definitions, or convert it to a function that returns a component
-   memoise expensive functions with `useMemo()`
    -   _remembers_ the last value and only runs the function if its dependent data changes
-   use fragments to wrap components: `<></>`
-   export one component per file
    -   in large projects, give each component its own directory (css, test, storybook etc.)
    -   this is the default setup for angular
    -   give your component a regular name & export it from index.tsx (barrel)
-   large bundles can cause the page to load slow initially
    -   nextjs + cra supports code splitting
    -   leverage dynamic imports to import code asynchronously
    -   in react we use lazy loading
    -   wrap it in a `<Suspense />` component to show a fallback while it's loading
-   avoid props drilling: passing state through intermediate components
    -   use redux or context api
    -   use the context sparingly, because any consuming component needs to be wrapped in a `Provider`
    -   global state is a fair use case
-   avoid prop 'plowing' (horizontal problem)
    -   use spread syntax to pass lots of props at once: `<User {...data} />`
-   use curried functions (function that wraps another function)
    -   e.g. onClick handler `<Comp onClick={curriedFunction(arg)} />`
-   avoid using useState with a large object, split into individual values & extract into a custom hook if necessary
    -   allows us to keep components 'dumb'

## Talks

[Custom Hooks in React: The Ultimate UI Abstraction Layer - Tanner Linsley | JSConf Hawaii 2020](https://www.youtube.com/watch?v=J-g9ZJha8FE&ab_channel=JSConf)

-   Custom hooks, e.g. useDarkMode, useOnClickOutside
-   Seperate contexts for store & dispatch to prevent unnecessary re-renders
-   Multiple contexts, server state
-   React Query

## Articles

[How to use React Context effectively - Kent C. Dodds](https://kentcdodds.com/blog/how-to-use-react-context-effectively)

-   Avoiding the use of default values when initialising contexts
-   Creating a custom Provider context, hook + workaround for React versions < 16.8.0 (hooks are favoured)
    -   Note: context itself is not exported
-   TypeScript workaround for initialising without default values, preventing need to do undefined checks later
-   Dispatching actions (no need for Action Creator abstraction)
-   Async actions & example of helper function within context module
    -   Reference to 'Advanced React Patterns' workshop
-   Context doesn't need to be global, favour multiple logically separated contexts in your app
