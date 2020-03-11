# questao
```
import Lista from '../Lista';

class Questao8{
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

export default Questao8;
```

# teste
```
import Questao8 from '../src/Lista_2/questao8';
import Lista from '../src/Lista';


let lista;
let list;
beforeEach(() => {
  lista = new Lista();
  list = new Questao8(lista);
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
