# React
Created: 02/07/2022 at 11:40
Tags; 
Related:

### What?
JavaScript library for building user interfaces.

```ad-warning
React is not the same as React Native
```

### Why?
- scalable development through reusable components
- flexible
- large development community


### JSX
HTML used like variables, and allows markup and logic to be together
```jsx
const name = 'Adam';
const element = <h1>Hello, {name}</h1>
```


### Components
Code that can be reused, usually defined as a function
```jsx
function Welcome(props){
	return <h1>Hello, {props.name}</h1>;
}
```

#### Props
Ways to customise components
```jsx
function Welcome({first_name, last_name}) {
	return <h1>Hello, {first_name} {last_name}</h1>;
}
```

#### Lifecycles
- Mounting
- Updating - when prop's or states change
- Unmounting

### Hooks
Removed the need for classes

#### useState
Easy way to store and set state

#### useEffect
Do things on re-renders, may need cleanup

### State
Ways to preserve values between re-renders