2022-07-11 11:12
Tags: #React #hoc
__
# React.memo
React. memo — это компонент высшего порядка (hoc). Не запускает перерисовку компоненты, если props которые приходят в неё, не изменились. 
```tsx
const UsersSecret = (props: {users: Array<string>}) => {  
    console.log('Users')  
    return <div>{props.users.map((el, i) => <div key={i}>{el}</div>)}</div>  
}

const Users = React.memo(UsersSecret)

//или

const Users = memo(props: {users: Array<string>}) => {  
    console.log('Users')  
    return <div>{props.users.map((el, i) => <div key={i}>{el}</div>)}</div>  
}
```

При оборачивании компонента с помощью `React.memo` React будет использовать последнюю отрисованную версию этого компонента. Мемоизация используется в приложениях React для повышения производительности.

---
Лучше всего использовать с [[useCallback]]
memo пишется в дочерней компоненте и следить за всеми пропсами
[[useCallback]] находиться в родительской компоненте и сдедит за всеми callBack

---
_Мемоизация — это метод_ оптимизации, используемый в основном для ускорения компьютерных программ _путем хранения результатов дорогостоящих_ вызовов функций и возврата кэшированного результата вычислений при повторном использовании тех же входных данных.
__
### Links
[[hoc]]