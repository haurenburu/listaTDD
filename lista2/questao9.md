# RACUNHO


## Questao 
```
import Lista from "../Lista";

class Questao9 {
  constructor() {
    this.lista1 = new Lista();
  }

  addPessoa(val1, val2) {
    if (isNaN(val1)) {
      this.nome = val1;
      this.idade = val2;
    } else {
      this.nome = val2;
      this.idade = val1;
    }

    this.lista1.append([this.nome, this.idade]);

    console.log(this.lista1.head.proximo.dado[0]);
    console.log(this.lista1.head.proximo.dado[1]);
  }
}

export default Questao9;
```

## Test

```
import Questao9 from "../src/Lista_2/Questao9";

let list;
beforeEach(() => {
  list = new Questao9();
});

test("123", () => {
  list.addPessoa("antonio", 22);
});

```