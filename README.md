# coding-best-practice

- 使用可选链代替函数兼容判断

```ts
// bad
if (func) func()
func() && func()

// good
func?.()
```

- Promise `fulfilled` 和 `rejected` 都需要处理的逻辑超过一条，统一放到 `finally`

```ts
// bad
promise
  .then((res) => {
    setLoading(false)
    closeModal()
    // ...
  })
  .catch((error) => {
    setLoading(false)
    closeModal()
  })

// good
promise
  .then((res) => {})
  .catch((error) => {})
  .finally(() => {
    setLoading(false)
    closeModal()
  })
```
