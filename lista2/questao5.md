# questao
```
shuffle() {
  for (let i = 0; i < this.size(); i++) {
    this.addAt(Math.floor(Math.random() * this.size()), this.removeEnd());
  }

  return this;
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