src = https://www.youtube.com/watch?v=Idf0zh9f3qQ

# Type alias vs Interface

## Syntax

```ts
type UserProps = {
  name: string;
  age: number;
}

type AdminProps = UserProps & {
  role: string;
}
```

```ts
interface UserProps {
  name: string;
  age: number;
}

interface AdminProps extends UserProps {
  role: string;
}
```

## Interface problem #1 - data type limitation

An interface can **only** describe an **object**, whereas a type alias can describe any data type.  

## Interface problem #2 - no union type

A type alias can also describe a **union type**, an interface cannot do that.
```ts
type Address = string | string[];
```

# Interface problem #3 - utility type syntax

A type alias can easily use **utility types**.  
An interface can too, but with an ugly syntax.  

```ts
type UserProps = {
    name: string;
    age: number;
    createdAt: Date;
}

type GuestProps = Omit<UserProps, 'age' | 'name'>; // only keep createdAt

// we could do the same with an interface
interface UserProps {
    name: string;
    age: number;
    createdAt: Date;
}

interface GuestProps extends Omit<UserProps, 'age' | 'name'> {}
```

# Interface problem #4 - Tuples syntax

```ts
type Address = [number, string];

interface Address extends Array<number | string> {
  0: number;
  1: string;
}
```
