
#react


```
### Key takeaways:
🌟
``` javascript
var array = [1,2,3,4,5];
console.log(array.at(0));
// In modern javasript we can use at function instead of doing this 'array[0]'
```

🌟

	Rendering : In react, rendering is not updating the dom or displaying elements on the screen. Rendering only happens inside react, it does not produce visual changes.

### Components:
#react

	It is the description of UI. It returns react element. Also it calls the react.createElement() method, when we invoke. Instances are created when we call a component, just like the below image.
	
![[Pasted image 20240411101943.png]]

![[Pasted image 20240411112028.png]]

![[Pasted image 20240411112757.png]]

	In this above, we can see the keyword named 'typeof', it is a react security feature which prevents us from the cross-site scripting attacks. If any hacker send an fake react element through api then it doesn't see the symbol and react doesn't include that fake element into the dom...

### How rendering works:
#react

![[Pasted image 20240411115319.png]]

### How renders are triggered : 
	The two situations that trigger renders:
		* Initial render of the application
		* State is updated in one or more component instances (re-render)
		
	Renders are not triggered immediately, but scheduled for when the JS engine has some free time. There is also batching of multiple setState calls in event handlers.

### Rendering Phase:

#### 1. Initial Render:
	Virtual DOM: Trees of all react elements created from all instances of component tree. Its cheap and fast to create multiple trees. Nothing to do with "Shadow dom"

	Rendering a component will cause all of its child components to be rendered as well (no matter if props changed or not)

	It is necessary to render child components also, because react doesn't know whether children will be affected.

#### 2. Render Phase:
	Why not update the entire dom whenever state changes somewhere in app ? 
		Because, that would be inefficent and wasteful. Writing to the dom is slow, Usually only a small part of the dom needs to be updated. React reuses as much of the existing dom as possible. Also here virtual dom is the javascript object, so it is cheap and fast.

	How react find which components to update ? 
		Reconciliation: Deciding which dom elements actually need to be inserted, deleted, or updated in order to reflect the latest state changes. Reconciliation is processed by reconciler which is the engine of the react. It's like the heart of the react. The current reconciler in react is called Fiber.


#### The Reconciler : Fiber

![[Pasted image 20240411125037.png]]

![[Pasted image 20240411125918.png]]

#### 3. The Commit Phase:

![[Pasted image 20240412100709.png]]

	Renderers: React-DOM, React-Native, Remotion are renderers. Actually they are not for rendering, they used to update the dom in commit phase.

### Diffing Rules:

	In diffing, if the component change its position or element as a update then the state of the component will reset. But if the component stays in a same element and position, also it only updated via props then it doesn't reset the state. The state stays the same.

### What is Key Prop:

	Special prop that used to tell the diffing algorithm that an element is unique. Allows react to distinguish between the multiple instances of the same component type. When a key stays the same across the renders, the element will be kept in the DOM (Even if the position in tree changes). When key prop changes in the element, and it will destroyed and new one will be created. In order to increase efficieny and reduce the unwanted dom changes use key in list.

### Refresher: Functional Programming Principles:

	Side Effects: Dependency on or modification of any data outside the function scope. "Interaction with the outside world". Examples: mutating external variables, HTTP requests, writing to DOM.

	Pure Function: Always gives the same output to the same input. Does not change any variables outside its scope.

	Impure Function: Output is unpredictable even if we give the same input.

### Rules for render logic:

	Components must be pure when it comes to render logic.
	Render logic produces no side effects.
	Do not perform network requests
	Do not start timers
	Do not use the DOM API
	Do not use or mutate the objects outside of the function scope
	Do not update state or refs: this will create an infinte loop.
	Side effects are allowed inside the event handler functions. There is also a special hood to register side effects (useEffect())

### How Event works in react:
![[Pasted image 20240412172307.png]]


### 

![[Pasted image 20240412174338.png]]