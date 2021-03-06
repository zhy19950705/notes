# Generics 泛型

## hello world of Generics

```typescript
function identify<T>(arg: T): T {
  return arg;
}
identify<number>(1);
```

## 泛型接口

```typescript
interface GenericIdentityFn<T> {
  (arg: T): T;
}

function identity<T>(arg: T): T {
  return arg;
}

let myIdentity: GenericIdentityFn<number> = identity;
```

## 泛型类

```typescript
class GenericNumber<T> {
  add: (x: T, y: T) => T;
}

let myGenericNumber = new GenericNumber<number>();
myGenericNumber.add = function(x, y) {
  return x + y;
};

myGenericNumber.add(1, 2); // 3
```

## 泛型约束

```typescript
interface lengthWise {
  length: number;
}

function getLength<T extends lengthWise>(arg: T): number {
  return arg.length;
}
```

## 泛型 类型参数

```typescript
function getProperty<T, K extends keyof T>(obj: T, key: K) {
  return obj[key];
}

getProperty({ a: 1, b: 2 }, 'b');
```

## 泛型 类类型

```typescript
function create<T>(c: { new (): T }): T {
  return new c();
}
```
