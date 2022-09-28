# <mark><b>Redux Notes</b></mark>

## <mark><b>Three Core Concepts: </b></mark>

### Cake Shop Scenario | Redux | Purpose

<br>
Shop | Store | Holds the state of the application

<br>
Intention to BUY_CAKE | Action | Describes what happend

<br>
Shopkeeper | Reducer | Ties the store and the action together

<br>
<mark>
<u><b>Definations</b></u></mark>
<br >

1. A STORE that holds the state of the application

2. A ACTION that describes the changes in the state of the application

3. A REDUCER that actually carries out the state transition depending on the transition

<mark><b>Principals</b></mark>
<br>

1. The state of the whole application is stored in an object tree within a single store. Maintain application state in a single object which is maintained by redux store. eg:

```js
{
  noOfCakes: 10;
}
```

2. The only way to change a state is to emit an action, object describing what happend. To update a state, inform redux with an action. Not allowed to directly update the state. eg:

```js
const BUY_CAKE = informing the shopkeeper know about the purchase

{
    type: BUY_CAKE
}
```

3. To specify how the state tree is transformed by actions, write pure reducers.
   Reducer - { previousState, action } => newState
   eg: Reducer is the shopkeeper

```js
const reducer = (state, action) => {
  switch (action.type) {
    case BUY_CAKE:
      return {
        numOfCakes: state.numOfCakes - 1,
      };
  }
};
```

## <b><mark>Redux Store</mark></b>

One store for the entire application. 
<br>
<u><b>Responsibilities: </b></u>
<br>
1. Holds application state
2. Allows access to state via getState()
3. Allows state to be updated via dispatch(action)
4. Registers listeners via subscribe(listener)
5. Handles unregistering of listeners via the function returned by the subscribe(listener)
