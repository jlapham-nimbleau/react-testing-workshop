Using this array:

```js
[{
  id: 1,
  label: "Apple",
},{
  id: 2,
  label: "Banana",
},{
  id: 3,
  label: "Carrot",
}]
```

Render each one in a list item in a React component?

```jsx
const food = [{
  id: 1,
  label: "Apple",
},{
  id: 2,
  label: "Banana",
},{
  id: 3,
  label: "Carrot",
}]

const List = () => {
  return (
    <ul>
      {food.map(item => (
        <li key={`${item.id}-${item.label}`}>{item.label}</li>
      ))}
    </ul>
  )
}
```
