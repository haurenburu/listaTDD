# questao
```
import ListaN from "../Lista";
import ListaD from "../ListaDuplamenteLigada";

class Questao8 {
  constructor(listaN) {
    this.listaD = new ListaD();
    this.listaN = listaN;
  }

  convert() {
    while (!this.listaN.isEmpty()) {
      this.listaD.add(this.listaN.removeEnd());
    }

    return this.listaD;
  }
}

export default Questao8;

```

# test

```
import Questao8 from "../src/Lista_2/Questao8";
import Lista from "../src/Lista";

test("asd", () => {
  let listN = new Lista();
  listN.append(1);
  listN.append(2);
  listN.append(3);
  listN.append(4);
  listN.append(5);

  let listD = new Questao8(listN);

  expect(listD.convert().toString()).toBe("1->2->3->4->5");
});

```