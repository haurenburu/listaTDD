

# lista
```
shuffle() {
  for (let i = 0; i < this.size(); i++) {
    this.addAt(Math.floor(Math.random() * this.size()), this.removeEnd());
  }

  return this;
}
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
import Lista from "../src/Lista";

let list;

beforeEach(() => {
  list = new Lista();
});

test("nome", () => {
  list.append(1);
  list.append(2);
  list.append(3);
  list.append(4);
  list.append(5);

  list.shuffle();

  expect(list.toString()).not.toEqual("1->2->3->4->5");
});

```
