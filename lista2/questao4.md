# questao
```
import Lista from "../Lista";

class Questao4 {
  constructor() {
    this.lista1 = new Lista();
    this.lista2 = new Lista();
  }

  push(el) {
    this.lista1.append(el);
  }

  pop() {
    return this.lista1.removeEnd();
  }

  reverse() {
    while (!this.lista1.isEmpty()) {
      this.lista2.append(this.lista1.removeEnd());
    }

    this.lista1 = this.lista2;

    return this.lista2;
  }
}

export default Questao4;

```
# lista
```
append(dado) {
  let novo_no = new Node(dado);

  if (this.isEmpty()) {
    this.head.proximo = novo_no;
  } else {
    let aux = this.head.proximo;
    while (aux.proximo !== null) {
      aux = aux.proximo;
    }
    aux.proximo = novo_no;
  }

  return novo_no.dado;
}

removeEnd() {
  if (this.isEmpty()) {
    throw new Error("A lista está vazia.");
  }

  let aux_a = this.head;
  let aux_b = this.head.proximo;
  let aux_c;

  while (aux_b.proximo !== null) {
    aux_a = aux_b;
    aux_b = aux_b.proximo;
  }
  aux_c = aux_b.dado;

  aux_b = null;
  aux_a.proximo = null;

  return aux_c;
}
```
# testes
```
import Questao4 from "../src/Lista_2/Questao4";

let list;

beforeEach(() => {
  list = new Questao4();
});

test("nome", () => {
  list.push(1);
  list.push(2);
  list.push(3);
  list.push(4);
  list.push(5);
  list.reverse();
  expect(list.pop()).toBe(1);
});

```