src = https://www.youtube.com/watch?v=Idf0zh9f3qQ

# Type alias vs Interface

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

# Interface problem #1

An interface can only describe an **object**, whereas a type alias can describe any data type.  

# Interface problem #2

A type alias can also describe a **union type**, an interface cannot do that.
```ts
type Address = string | string[];
```

# Interface problem #3

A type alias can easily use utility types.  
An interface can too but with ugly syntax.  

```ts

```
