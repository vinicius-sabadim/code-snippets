# Code snippets

## Javascript

- Generate a random number between a range

```javascript
function generateNumberInRange(min, max) {
  return Math.floor(Math.random() * (max - min + 1) + min)
}
```

- Generate an array with starting values

```javascript
Array(HOW_MANY_ELEMENTS)
  .fill(null)
  .map(() => {})
```

- Format a number according to a language

```javascript
const number = 123456.789
new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(
  number
)
```

- Check for a click in an element that contains a class (great for check clicks outside something)

```javascript
element.addEventListener('click', e => {
  if (e.target.classList.contains(<className>)) {
    // The clicked element will have the className
  }
})
```

## React

- Create a provider and use it as a hook

```javascript
import React from 'react'

const AppStateContext = React.createContext()

function AppProvider({ children }) {
  const [state, setState] = React.useState()

  return (
    <AppStateContext.Provider value={state}>
      {children}
    </AppStateContext.Provider>
  )
}

function useAppState() {
  const context = React.useContext(AppStateContext)
  if (context === undefined) {
    throw new Error('useAppState must be used within a AppProvider')
  }
  return context
}

export { AppProvider, useAppState }
```

- CSS-in-JS using media query

```javascript
const mq = window.matchMedia('(max-width: 600px)')

if (mq.matches) {
  // Do something
}
```