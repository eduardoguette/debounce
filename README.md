# Debounce 


Un script que solo hace una cosa, ahorrar bytes.

```
function debounce(callback, wait, callFirst) {
  let timerId;
  let call = callFirst;
  return (...args) => {
    if (call) {
      callback(...args);
      call = false;
      return;
    }
    clearTimeout(timerId);
    timerId = setTimeout(() => {
      callback(...args);
      call = callFirst;
    }, wait);
  };
}
```


```
 const fn1 =  debounce(() => { console.log("click")}, 2000)
    fn1();
    fn1();
    fn1(); Solo se ejecuta una vez, cuando terminen todas las llamadas. 
    
```

```
 const fn1 =  debounce(() => { console.log("click")}, 2000, true)
    fn1(); Se ejecuta inmediatamente
    fn1();
    fn1(); al terminar la última llamada se ejecuta una vez más. 
    
```
### Ejemplo

- [CodePen](https://codepen.io/eduardoguette/pen/qBjbQRO?editors=1011)

### Documentación 
- [freeCodeCamp](https://www.freecodecamp.org/espanol/news/curso-debounce-javascript-como-hacer-que-tu-js-espere/)
- [Just](https://github.com/angus-c/just#just-debounce-it)
