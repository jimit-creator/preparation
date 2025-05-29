
---

## 1. How to reset state in Redux?

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

## 2. React Context vs React Redux

| Feature         | React Context            | Redux                     |
|------------------|---------------------------|-----------------------------|
| Purpose          | Prop drilling solution    | State management            |
| Performance      | Rerenders all consumers   | Optimized with selectors    |
| Middleware       | Not supported             | Supports thunk, saga, etc.  |
| Tools            | Simple, minimal setup     | Advanced debugging tools    |

✅ Use Context for simple data, Redux for complex logic.

---

## 3. Proper Way to Access Redux Store

Use `useSelector` and `useDispatch` from `react-redux`.

```jsx
const count = useSelector(state => state.counter);
const dispatch = useDispatch();
dispatch({ type: 'INCREMENT' });
```

---

## 4. What is Redux Thunk?

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

## 5. What is Redux Saga?

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

## 6. Redux Saga vs Redux Thunk

| Feature       | Thunk                  | Saga                         |
|---------------|------------------------|-------------------------------|
| Syntax        | Functions              | Generator functions           |
| Readability   | Simple async calls     | Better for complex flows      |
| Testing       | Harder to test         | Easier to test (step by step) |

---

## 7. What is Redux DevTools?

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

## 8. React vs React Native

| Feature         | React               | React Native               |
|------------------|----------------------|------------------------------|
| Platform         | Web (HTML, DOM)     | Mobile (iOS, Android)        |
| Render Targets   | Browser DOM         | Native components            |
| Styling          | CSS                 | Stylesheets in JS            |

---

## 9. What is React.memo?

HOC that prevents re-render if props haven't changed.

### Example:
```jsx
const MyComponent = React.memo(({ name }) => <div>{name}</div>);
```

✅ **Benefits:** Improves performance by avoiding unnecessary renders.

---

## 10. Prevent Unnecessary Updates using setState

```js
if (this.state.count !== newCount) {
  this.setState({ count: newCount });
}
```

✅ Use `shouldComponentUpdate` or `React.memo` in functional components.

---

## 11. What are Default Props?

Default values for props if none passed.

```jsx
MyComponent.defaultProps = {
  name: 'Guest'
};
```

---

## 12. Different Design Patterns in React

- Container/Presentational
- Higher-Order Components (HOC)
- Render Props
- Hooks pattern
- Compound components

---

## 13. PropTypes in React

Used to validate props in development.

```jsx
MyComponent.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number
};
```

---

## 14. Hooks You’ve Used

- `useState`, `useEffect`, `useRef`, `useContext`
- `useReducer`, `useMemo`, `useCallback`
- Custom Hooks

---

## 15. createElement vs cloneElement

| Feature             | createElement                       | cloneElement                        |
|---------------------|-------------------------------------|-------------------------------------|
| Purpose             | Create a new element                | Clone an existing element           |
| Syntax              | `React.createElement('div')`        | `React.cloneElement(element)`       |
| Use Case            | Building JSX from scratch           | Modify props of an existing child   |

---
