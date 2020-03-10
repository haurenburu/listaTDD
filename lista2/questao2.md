# questao
import Lista from "../Lista";

class Questao2 {
  constructor() {
    this.lista = new Lista();
  }

  enqueue(el) {
    return this.lista.add(el);
  }

  dequeue() {
    return this.lista.removeEnd();
  }

  size() {
    return this.lista.size();
  }
}

export default Questao2;


# lista
```
add(dado) {
  let novo_no = new Node(dado);

  novo_no.proximo = this.head.proximo;
  this.head.proximo = novo_no;

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
import Questao2 from "../src/Lista_2/Questao2";

let list;

beforeEach(() => {
  list = new Questao2();
});

test("Pilha: ", () => {
  list.enqueue(1);
  list.enqueue(2);
  list.enqueue(3);
  list.enqueue(4);
  list.enqueue(5);
  expect(list.dequeue()).toBe(1);
});

```