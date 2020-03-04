# Fracao
```
class Fracao {
  constructor(numerador = 1, denominador = 1) {
    if(denominador === 0) {
      throw new Error("Denominador nao pode ser 0!");
    }
    this.dados = [numerador, denominador];
  }

  multiplicar(frac) {
    let nume = this.dados[0] * frac.dados[0];
    let deno = this.dados[1] * frac.dados[1];

    return new Fracao(nume, deno);
  }

  dividir(frac) {
    let nume = this.dados[0] * frac.dados[1];
    let deno = this.dados[1] * frac.dados[0];

    return new Fracao(nume, deno);
  }

  toString() {
    return `${this.dados[0]}/${this.dados[1]}`;
  }
}

export default Fracao;
```

# Teste
```
import Fracao from "../src/Fracao";


let frac1, frac2;

beforeEach(()=>{
  frac1 = new Fracao(2, 3);
  frac2 = new Fracao(4, 5);
});

test("multiplicar: ", ()=> {
  expect(frac1.multiplicar(frac2).toString()).toBe('8/15');
})

test("dividir: ", ()=> {
  expect(frac1.dividir(frac2).toString()).toBe('10/12');
})

test("divisao por 0: ", () => {
  expect(() => {
    new Fracao(5,0);

  }).toThrowError("Denominador nao pode ser 0!")
});
```
