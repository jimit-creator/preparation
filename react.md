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
