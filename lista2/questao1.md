# questao
```
import Lista from "../Lista";

class Questao1 {
  constructor() {
    this.lista = new Lista();
  }

  push(el) {
    return this.lista.append(el);
  }
  pop() {
    return this.lista.removeEnd();
  }
  size() {
    return this.lista.size();
  }
}

export default Questao1;
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
let list;

beforeEach(() => {
list = new Questao1();
});

test("Pilha: ", () => {
list.push(1);
list.push(2);
list.push(3);
list.push(4);
list.push(5);
expect(list.pop()).toBe(5);
});
```