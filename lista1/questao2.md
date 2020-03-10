# pilha
```
questao2() {

  let aux = new Pilha(this.maxSize);
  let fin = new Pilha(this.maxSize);

  for(let i = 0; i < this.maxSize; i++) this.push(i);

  fin.push(this.pop());
  for(let i = 0; i < this.maxSize-2;i++) aux.push(this.pop());
  for(let i = 0; i < this.maxSize-2;i++) fin.push(aux.pop());
  fin.push(this.pop());

  return fin;
}

```
# Teste

```
import Pilha from "../src/Pilha";

let p;

beforeEach(() => {
  p = new Pilha(5);
});

test("questao 2", () => {
  expect(p.questao2().top()).toBe(0)
});


```