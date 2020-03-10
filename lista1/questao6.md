# DeQ
```
class DeQ {
  constructor(size = 10) {
    this.dado = [];

    this.vfront = -1;
    this.vrear = -1;

    this.maxSize = size;
  }

  insertFront(el) {
    if(this.isFull()) {
      throw new Error("Overflow");
    }
    else if(this.vfront === 0){
      throw new Error("Front Full");
    } 
    else if(this.isEmpty()) {
      this.vfront = this.vrear = 0;
    }
    else {
      this.dado[this.vfront--] = el;
    }
  }

  insertRear(el) {
    if(this.isFull()) throw new Error("Overflow");
    else if(this.isEmpty()) {
      this.vfront = this.vrear = 0;
    }
    this.dado[this.vrear++] = el;
  }

  removeFront() {
    if(this.isEmpty()) throw new Error("Underflow");
    else if (this.size() === 1) {
      let temp = this.vfront;
      this.vfront = this.vrear = -1
      return this.dado[temp];
    }
    return this.dado[this.vfront++];
  }

  removeRear() {
    if(this.isEmpty()) throw new Error("Underflow");
    else if (this.size() === 1) {
      let temp = this.vrear;
      this.vfront = this.vrear = -1;
      return this.dado[temp];
    }
    return this.dado[this.vrear--];
  }

  size() {
    if(this.vfront === 0 && this.vrear === 0) return 1;
    return this.vrear - this.vfront;
  }
  
  isEmpty() {
    return this.vrear === this.vfront;
  }
  
  isFull() {
    return this.size() === this.maxSize;
  }

  rear() {
    if(this.isEmpty()) throw new Error("Underflow");
    return this.vrear;
  }
  
  front() {
    if(this.isEmpty()) throw new Error("Underflow");
    return this.vfront;
  }
}

export default DeQ;
```

# test

```
import DeQ from '../src/DeQ';

let dq;

beforeEach(() => {
  dq = new DeQ(5);
})

test("insert rear: ", () => {
  dq.insertRear(2)
  dq.insertRear(2)
  dq.insertRear(2)
  expect(dq.size()).toBe(3);  
});

test("insert front: ", () => {
  dq.insertFront(2)
  expect(dq.size()).toBe(1);  
});


test("front full: ", () => {
  dq.insertFront(2)

  expect(() =>{
    dq.insertFront(5);
  }).toThrowError("Front Full")
}); 

test("insert after remove front: ", () => {
  dq.insertFront(5);
  dq.insertRear(3)
  dq.insertRear(2)
  dq.removeFront()
  dq.insertFront(5);
  expect(dq.front()).toBe(0);

});

test("remove multiple fronts: ", () => {
  dq.insertRear(2);
  dq.insertRear(3);
  dq.insertRear(4);
  dq.insertRear(5);
  dq.insertRear(6);
  dq.removeFront();
  dq.removeFront();
  dq.removeFront();
  expect(dq.removeFront()).toBe(5)
});

test("remove front: ", () => {
  dq.insertRear(1)
  dq.insertRear(2)
  dq.insertRear(3)
  dq.insertRear(4)
  dq.insertRear(5)
  dq.removeFront()
  dq.removeFront()
  expect(dq.removeFront()).toBe(3);  
}); 

```