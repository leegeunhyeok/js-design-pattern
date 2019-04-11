# 싱글톤 패턴

```javascript
// IIFE
const ImportantManager = (() => {
  let instance = null

  // instance가 null인 경우에 처음 1회만 호출됨
  const init = () => {
    return {
      impVariable1: 'JS',
      impVariable2: 100
    }
  }

  return {
    getInstance () {
      if (instance === null) {
        instance = init()
      }
      return instance
    }
  }

})()

const a = ImportantManager.getInstance()
const b = ImportantManager.getInstance()
const c = { impVariable1: 'JS', impVariable2: 100 }

console.log(a === b) // true
console.log(a === c) // false

```

Write : `2019.04.11`  
Update: `-`
