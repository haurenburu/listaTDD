# questao
```
import Lista from '../Lista';

class Questao6{
  constructor(lista){
    this.lista = lista;
  }
  substring(start, finish) {
    let aux = new Lista();
    let cont = 0;
    while (!this.lista.isEmpty()) {
      let a = this.lista.removeEnd();
      if(cont >= start && cont <= finish){
        aux.append(a);  
      }
      cont++;
    }
    let a = aux.toString();
    return a;
  }

  append(el) {
    this.lista.add(el);
  }

  toString() {
    return this.lista.toString();
  }

}

export default Questao6;
```

# teste
```
import Questao6 from '../src/Lista_2/questao6';
import Lista from '../src/Lista';


let lista;
let list;
beforeEach(() => {
  lista = new Lista();
  list = new Questao6(lista);
});


test("asdas", () => {

  list.append('a');
  list.append('b');
  list.append('c');
  list.append('d');
  list.append('e');
  list.append('f');

  expect(list.substring(1,2)).toBe("b->c");

});
```
