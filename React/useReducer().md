#react
### State with UseReducer:

	An alternate way of setting state, ideal for complex state, and related pieces of state.
	Store related pieces of state in a state object
	useReducer needs reducer function which contains all logic to update state. Decouples state logic from all the components
	reducer: pure function (no side effects) that takes current state and action and returns the next state.
	action: object that describes how to update state. with the help of action.type and action.payload we can derive the logic of how to update the state.
	dispatch: function to trigger state updates, by "sending actions" from event handlers to the reducer 

### UseState vs UseReducer

	UseState: Ideal for single, independent pieces of state (numbers, strings, single arrays,etc.)
	Logic to updata state is placed directly in event handlers or effects, spread all over one or multiple components.
	State is updated by calling setState function.
	Imperative state updates

	UseReducer: Ideal for multiple related pieces of state and complex state (e.g. object with many values and nested objects or arrays)
	Logic to update state lives in one central place, decoupled from components: the reducer
	State is updated by dispatching an action to reducer.
	Declarative state updates: Complex state transitions are mapped to actions