Refactor this code to use Context instead of props:

```js
import { createContext, useState } from "react"

export const UserContext = createContext()

export const UserContextProvider = ({ children }) => {
  const [message, setMessage] = useState({
    message: "Hello, world!",
  })

  return (
    <UserContext.Provider value={{ message, setMessage }}>
      {children}
    </UserContext.Provider>
  )
}

<UserContextProvider>
  function Outer(){
    return (
      <Middle />
    )
  }

  function Middle(){
    return (
      <Inner />
    )
  }

  function Inner(){
    const { message, setMessage } = useContext(UserContext)
    return (
      <p>{ message }</p>
    )
  }
</UserContextProvider>
```

---

Refactor this code to use Context instead of props:

```js
function Outer(){
  const [user, setUser] = useState("Bill")
  const logout = () => setUser("null")

  return (
    <Middle logout={ logout } />
  )
}

function Middle({ logout }){
  return (
    <Inner logout={ logout } />
  )
}

function Inner({ logout }){
  return (
    <button onClick={ logout }>Logout</button>
  )
}
```
