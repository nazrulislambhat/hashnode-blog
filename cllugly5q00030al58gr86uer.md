---
title: "React Hooks Explained"
seoTitle: "A Comprehensive Guide to React Hooks: Revolutionizing Component Develo"
seoDescription: "Discover the power of React Hooks, a game-changing feature introduced after React 16.8. Learn how these hooks, such as useState, useEffect, useContext"
datePublished: Mon Aug 28 2023 05:49:18 GMT+0000 (Coordinated Universal Time)
cuid: cllugly5q00030al58gr86uer
slug: react-hooks-explained
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693201702863/069490a8-2638-45dc-8c7a-e593d715623d.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693201708444/c34b543c-be17-4b44-adf8-a38007583687.jpeg
tags: reactjs, hooks, react-hooks, usestate

---

Before React Hooks came along (this was before React version 16.8), developers had to write class components to make use of certain features in React. However, with the introduction of React Hooks, a more user-friendly way to build components emerged. This is because React Hooks allow us to use stateful logic without needing to change the structure of our components.

There are a total of 10 Hooks that provide various capabilities:

1. **useState:** This is one of the most essential and frequently used Hooks. It's used to manage reactive data, which refers to any data that changes within the application. Whenever any of this data changes, React automatically updates the user interface. For example:
    
    ```javascript
    const [count, setCount] = React.useState(0);
    ```
    
2. **useEffect:** This Hook lets us incorporate all the lifecycle functionalities using a single function API. It runs under different circumstances:
    
    * Upon component mounting and whenever stateful data changes.
        
    * When the component initializes for the first time.
        
    * Only when a specific state (like `count`) changes.
        
    * Before the component is removed from the user interface.
        
3. **useContext:** This Hook simplifies working with React's Context API. Context allows data sharing within a component tree without the need to pass data through props. It eliminates the need for prop-drilling. For instance:
    
    ```javascript
    const ans = {
        right: '✅',
        wrong: '❌'
    };
    
    const AnsContext = createContext(ans);
    
    function Exam(props) {
        return (
            <AnsContext.Provider value={ans.right}>
                <RightAns />
            </AnsContext.Provider>
        );
    }
    
    function RightAns() {
        const ans = React.useContext(AnsContext);
        return <p>{ans}</p>;
    }
    ```
    
4. **useRef:** This Hook enables us to create a mutable object. It's often used when values keep changing, similar to how `useState` operates. The key distinction is that `useRef` doesn't trigger re-renders when the value changes. An example:
    
    ```javascript
    function App() {
        const myBtn = React.useRef(null);
        const handleBtn = () => myBtn.current.click();
    
        return (
            <button ref={myBtn} onClick={handleBtn}>
            </button>
        );
    }
    ```
    
5. **useReducer:** This Hook shares similarities with `setState`, but it offers a different approach to state management using the Redux pattern. Instead of directly modifying the state, we dispatch actions that are handled by a reducer function, which determines the next state.
    
6. **useMemo:** This Hook aids in optimizing computational costs and performance. It's employed when we need to perform resource-intensive calculations.
    
7. **useCallback:** This Hook is used to memoize functions, particularly when those functions need to maintain specific dependencies. It's useful for preventing unnecessary re-renders of child components.
    
8. **useImperativeHandle:** This Hook is used to modify the exposed ref of a component. It's not frequently used.
    
9. **useLayoutEffect:** Similar to `useEffect`, this Hook runs after rendering but before updates are displayed on the screen. It's commonly used to measure elements before they're visually updated.
    
10. **useDebugValue:** This Hook might seem odd, but it's helpful for defining custom labels in React Dev Tools. These labels assist in debugging. It's used in tandem with other Hooks to provide more context and information to the developer when debugging.
    

All these Hooks collectively provide a comprehensive toolset for building React components in a more streamlined and efficient manner. If you'd like to delve deeper into each Hook's functionalities, you can refer to [Fireship's YouTube video](https://youtu.be/TNhaISOUy6Q) on React Hooks.