# React

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
