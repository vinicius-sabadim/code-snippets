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
