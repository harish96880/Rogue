#react #useEffect
### Component lifecycle:

	Mount / Render - Component instance is rendered for first time / Fresh state and props are created

	Re-render - State Changes / Props Changes / Parent - rerenders / Context Changes

	Unmount - Component instance is destroyed and removed / State and props are destroyed

### Side Effect:

	A side effect is basically any "interaction between a React component and the world outside the component. We can also think of a side as " code that actually does something". Example: Data fetching, setting up subscriptions, setting up timers, manually accessing the DOM, etc. We can create side effect in two places in react. 1. Event handlers, 2. UseEffect()

### useEffect():

		The Dependancy Array: By default, effects run after every render. We can prevent that by passing a dependancy array.
		Without dependancy array, react doesn't know when to run the effect.
		Each time one of the dependencies changes, the effect will be executed again.
		Every state variable and props used in useEffect, must be included in the dependancy array.
		The mechanics of effect: UseEffect is like an event listener that is listening for one dependency to change. Whenever dependency changes, it will execute the effect again.
		It is asynchronous, runs after browser paint process. Some times it takes too much time to fetch, so before the results came, browser paint also happens.
		Cleanup functions in react: We can use cleanup function after the useEffect() and before the useEffect(). For example, We can avoid racing condition in fetching using cleanup functions. AbortController responsible for clearing racing condition in fetching.

### React Hooks:

	Special built-in functionality that allow us to "hook" into React internals. Creating and accessing the state from the fiber tree. Registering side effects from the fiber tree. Manual DOM selections. Always starts with "use".

