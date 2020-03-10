# Pilha

```
convert(num) {
  let pilha = new Pilha(8);
  
  for (let i = num; i >= 0; i--) {
    pilha.push(parseInt(num % 2))
    num /= 2;
  }
  for(let i =0; i < 8; i++)
  this.push(pilha.pop());
}

```

# Teste

```
test("questao 4", () => {
  let pil = new Pilha(8);
  pil.convert(7);
  expect(pil.print()).toBe("[ 0 0 0 0 0 1 1 1 ]");
});
```