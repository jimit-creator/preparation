# React Interview Questions & Answers (Simple Explanation)

This document provides simple, clear answers to commonly asked React interview questions with small examples and benefits explained.

---

## 1. What is React?
React is a JavaScript library for building user interfaces, mainly used for single-page applications.

### ✅ Advantages
- Reusable Components
- Virtual DOM improves performance
- Unidirectional Data Flow
- Strong ecosystem

### ❌ Disadvantages
- Learning curve (JSX, hooks, etc.)
- Fast updates can be overwhelming
- Requires third-party libraries

---

## 2. Props and State in React
- **Props** are read-only and passed from parent to child.
- **State** is local and can be changed inside the component.

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

```jsx
function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>Clicked {count} times</button>;
}
```

---

## 3. What is a Hook in React?
Hooks let you use state and lifecycle in function components.

### 🔹 Common Hooks
- useState, useEffect, useRef, useContext

### 🎯 Benefits
- Reuse logic
- Cleaner code

### 🧩 Custom Hook Example
```jsx
function useCounter(initialValue = 0) {
  const [count, setCount] = useState(initialValue);
  const increment = () => setCount(c => c + 1);
  return [count, increment];
}
```

Rules:
- Start with `use`
- Call only at the top level

---

## 4. What are Pure Components?
Only re-render when props/state change.

```jsx
class MyComponent extends React.PureComponent {
  render() {
    return <div>{this.props.name}</div>;
  }
}
```

---

## 5. What are Synthetic Events?
React's wrapper around browser events for consistency.

```jsx
<button onClick={(e) => alert(e.type)}>Click me</button>
```

---

## 6. What is the Virtual DOM?
A virtual copy of the real DOM. React uses it for efficient updates.

### 🔁 How it works
1. Renders to Virtual DOM.
2. Compares (diffs) with old.
3. Updates only changed parts.

---

## 7. Virtual DOM vs Shadow DOM

| Feature         | Virtual DOM         | Shadow DOM                      |
|----------------|---------------------|---------------------------------|
| Used by        | React               | Web Components                  |
| Purpose        | Performance         | Style encapsulation             |
| Scope          | Whole App UI        | One Component                   |

---

## 8. Controlled vs Uncontrolled Components

- **Controlled**: React manages the form input.
```jsx
<input value={name} onChange={(e) => setName(e.target.value)} />
```
- **Uncontrolled**: DOM manages input.
```jsx
<input ref={inputRef} />
```

---

## 9. What is Lifting State Up?
Move shared state to a common parent.

```jsx
function Parent() {
  const [value, setValue] = useState('');
  return <>
    <ChildA value={value} />
    <ChildB onChange={setValue} />
  </>;
}
```

---

## 10. What are Higher-Order Components?
A function that returns a new component with added features.

```jsx
function withLogger(Component) {
  return function Wrapped(props) {
    console.log('Props:', props);
    return <Component {...props} />;
  };
}
```

---

## 11. What is the children prop?
Special prop to pass nested elements.

```jsx
function Wrapper({ children }) {
  return <div>{children}</div>;
}

<Wrapper><p>Hello inside!</p></Wrapper>
```

---

## 12. What is Reconciliation?
React compares virtual DOM trees and updates the real DOM efficiently.

---

## 13. Stateless vs Stateful Components

- Stateless: No state, just UI.
```jsx
function Greeting({ name }) {
  return <h1>Hello {name}</h1>;
}
```
- Stateful: Manages internal state.
```jsx
function Counter() {
  const [count, setCount] = useState(0);
  return <p>{count}</p>;
}
```

---

## 14. What are Fragments?
Used to group elements without extra nodes.

```jsx
<>
  <h1>Title</h1>
  <p>Text</p>
</>
```

---


## 15. What is JSX?
JSX stands for JavaScript XML. It allows writing HTML inside JavaScript.

```jsx
const element = <h1>Hello JSX!</h1>;
```

✅ **Why it's useful?** Easier to write UI code. Looks like HTML but it's converted to JavaScript.

---

## 16. What is Props Drilling?
Passing data from parent to child to child (deeply nested).

### ❌ Disadvantages:
- Hard to maintain
- Components become dependent

### ✅ How to avoid:
- Use React Context API or state management tools (like Redux)

---

## 17. What are Refs in React?
Refs give direct access to DOM elements.

```jsx
const inputRef = useRef();
<input ref={inputRef} />
```

✅ **Why useful?** For focus, animations, or third-party DOM manipulations.

---

## 18. What is Forward Ref?
Allows parent to access child component’s ref.

```jsx
const FancyInput = forwardRef((props, ref) => <input ref={ref} />);
```

---

## 19. What are Error Boundaries?
Special components to catch runtime errors in child components.

```jsx
class ErrorBoundary extends React.Component {
  componentDidCatch(error, info) { ... }
  render() {
    return this.props.children;
  }
}
```

✅ **Why required?** Prevent app crashes and show fallback UI.

---

## 20. What is useCallback?
Returns memoized version of a callback.

```jsx
const handleClick = useCallback(() => {
  console.log("Clicked");
}, []);
```

✅ **Benefits:** Prevents re-creating functions, avoids unnecessary re-renders.

---

## 21. useMemo vs useCallback

| useMemo                          | useCallback                     |
|----------------------------------|----------------------------------|
| Returns a **memoized value**     | Returns a **memoized function** |
| `useMemo(() => compute, [])`     | `useCallback(() => fn, [])`     |

---

## 22. What is Lazy Loading?
Loads components only when needed.

```jsx
const LazyComponent = React.lazy(() => import('./Component'));
```

✅ **Why required?** Improve performance by splitting code.

---

## 23. What is Suspense?
Used with lazy loading to show fallback UI while loading.

```jsx
<Suspense fallback={<div>Loading...</div>}>
  <LazyComponent />
</Suspense>
```

---

## 24. What is Context in React?
Provides global data to components without props drilling.

```jsx
const MyContext = React.createContext();
<MyContext.Provider value="Hello">
  <Child />
</MyContext.Provider>
```

✅ **Benefits:** Cleaner code, avoids props drilling.

---

## 25. Passing Data from Child to Parent

- **Using Callback**:
```jsx
function Parent() {
  const getData = (data) => console.log(data);
  return <Child onSend={getData} />;
}
function Child({ onSend }) {
  onSend("Data from child");
}
```

- **Using Context or global state (like Redux)**

---

## 26. How to Optimize React App?
- Memoization (`React.memo`, `useMemo`, `useCallback`)
- Code splitting (`React.lazy`)
- Avoid unnecessary state
- Use keys in lists
- Avoid inline functions

---

## 27. What are React Mixins?
Old way to reuse logic in components (used in class components).

✅ **Why not used now?** Replaced by Hooks and HOCs.

---

## 28. What is Redux?
A state management library.

```jsx
dispatch({ type: "INCREMENT" })
```

✅ **Why required?**
- Centralized state
- Easy debugging
- Predictable

---


## 29. How to reset state in Redux?

You can reset state by listening to a specific action in your root reducer.

### Example:
```js
const appReducer = combineReducers({
  user: userReducer,
  posts: postReducer
});

const rootReducer = (state, action) => {
  if (action.type === 'RESET') {
    state = undefined;
  }
  return appReducer(state, action);
};
```

Dispatch `dispatch({ type: 'RESET' })` to reset entire state.

---

## 30. React Context vs React Redux

| Feature         | React Context            | Redux                     |
|------------------|---------------------------|-----------------------------|
| Purpose          | Prop drilling solution    | State management            |
| Performance      | Rerenders all consumers   | Optimized with selectors    |
| Middleware       | Not supported             | Supports thunk, saga, etc.  |
| Tools            | Simple, minimal setup     | Advanced debugging tools    |

✅ Use Context for simple data, Redux for complex logic.

---

## 31. Proper Way to Access Redux Store

Use `useSelector` and `useDispatch` from `react-redux`.

```jsx
const count = useSelector(state => state.counter);
const dispatch = useDispatch();
dispatch({ type: 'INCREMENT' });
```

---

## 32. What is Redux Thunk?

Middleware that allows action creators to return a function instead of an object.

### Example:
```js
const fetchData = () => (dispatch) => {
  dispatch({ type: "LOADING" });
  fetch('/api/data')
    .then(res => res.json())
    .then(data => dispatch({ type: "SUCCESS", payload: data }));
};
```

✅ **Benefits:** Handles async logic inside actions.

---

## 33. What is Redux Saga?

Saga uses generator functions to handle side effects.

### Example:
```js
function* fetchUser() {
  const data = yield call(api.getUser);
  yield put({ type: "SET_USER", payload: data });
}
```

✅ **Why Saga?**
- Easier to test
- Handles complex async flows

---

## 34. Redux Saga vs Redux Thunk

| Feature       | Thunk                  | Saga                         |
|---------------|------------------------|-------------------------------|
| Syntax        | Functions              | Generator functions           |
| Readability   | Simple async calls     | Better for complex flows      |
| Testing       | Harder to test         | Easier to test (step by step) |

---

## 35. What is Redux DevTools?

Browser extension to inspect Redux actions and state.

✅ **Features**:
- Time travel debugging
- Action logger
- State inspection
- Undo/Redo

### Setup:
```js
const store = createStore(reducer, window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__());
```

---

## 36. React vs React Native

| Feature         | React               | React Native               |
|------------------|----------------------|------------------------------|
| Platform         | Web (HTML, DOM)     | Mobile (iOS, Android)        |
| Render Targets   | Browser DOM         | Native components            |
| Styling          | CSS                 | Stylesheets in JS            |

---

## 37. What is React.memo?

HOC that prevents re-render if props haven't changed.

### Example:
```jsx
const MyComponent = React.memo(({ name }) => <div>{name}</div>);
```

✅ **Benefits:** Improves performance by avoiding unnecessary renders.

---

## 38. Prevent Unnecessary Updates using setState

```js
if (this.state.count !== newCount) {
  this.setState({ count: newCount });
}
```

✅ Use `shouldComponentUpdate` or `React.memo` in functional components.

---

## 39. What are Default Props?

Default values for props if none passed.

```jsx
MyComponent.defaultProps = {
  name: 'Guest'
};
```

---

## 40. Different Design Patterns in React

- Container/Presentational
- Higher-Order Components (HOC)
- Render Props
- Hooks pattern
- Compound components

---

## 41. PropTypes in React

Used to validate props in development.

```jsx
MyComponent.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number
};
```

---

## 42. Hooks You’ve Used

- `useState`, `useEffect`, `useRef`, `useContext`
- `useReducer`, `useMemo`, `useCallback`
- Custom Hooks

---

## 43. createElement vs cloneElement

| Feature             | createElement                       | cloneElement                        |
|---------------------|-------------------------------------|-------------------------------------|
| Purpose             | Create a new element                | Clone an existing element           |
| Syntax              | `React.createElement('div')`        | `React.cloneElement(element)`       |
| Use Case            | Building JSX from scratch           | Modify props of an existing child   |

---
