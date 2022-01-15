# Provider Pattern
### Make data available to multiple child components

In some cases, we want to make available data to many (if not all) components in an application. 
Although we can pass data to components using props, this can be difficult to do if almost all
components in your application need access to the value of the props.

---
This is where the Provider Pattern can help us out! With the Provider Pattern, 
we can make data available to multiple components. Rather than passing that 
data down each layer through props, we can wrap all components in a Provider. 
A Provider is a higher order component provided to us by the a Context object. 
We can create a Context object, using the createContext method that React provides for us.
```js
const DataContext = React.createContext()

function App() {
  const data = { ... }

  return (
    <div>
      <DataContext.Provider value={data}>
        <SideBar />
        <Content />
      </DataContext.Provider>
    </div>
  )
}
```
