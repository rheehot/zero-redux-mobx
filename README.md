## Redux and MobX course by Zerocho

1. Reducer
2. Initial State
3. Store (createStore)
4. Actions
5. Dispatch

### Process

1. Store 에 글로벌 State가 담긴다.
2. Action을 실행한다.
3. Middleware 
4. 실행된 Action 을 통해 State 가 변화된다.

### Reducers

Action을 Dispatch 하면 Reducer가 새로운 State 를 만들어준다.

- 불변성을 유지해야 함.
- 기존의 state 는 새로운 state 로 **대체** 됨.
- 첫번째 인자로는 prevState
- 두번째 인자로는 action
- Action 이 많아지면 Reducer의 Case 도 늘어나게 됨. (Action과 서로 짝을 이뤄야 함.)

### Store

- `createStore( reducer, initialState: object )`;

#### store.subscribe

Store의 변화를 감지하는 이벤트 리스너

```jsx
store.subscribe(() => {
    console.log(changed)
})
```

### Actions

- 액션은 함수로 보통 선언되지만 액션은 `객체` 이다. 함수로 return 되는 객체가 액션이다. 액션을 동적으로 만들어 내기 위해 함수를 사용하는 것이다. ( Action Creator )
- 액션은 이름을 가지고 있어야 한다. 이름은 보통 `type` 으로 선언된다. 그리고 보통 All 대문자로 표현한다. `(ex) CHANGE_NAME`
- 액션을 만들 때에는 내가 기존 State 를 어떻게 바꾸고 싶다. 라는 생각으로 State 기준으로 작성한다.
- 액션이 있으면 항상 짝이 맞는 Reducer 가 존재해야 한다.

### Dispatch

Dispatch 는 **실행**을 의미한다. 위 모든 과정은 미리 셋팅을 해야 하고, Dispatch는 실제로 만들어놓은 Action을 실행할 때 사용한다.