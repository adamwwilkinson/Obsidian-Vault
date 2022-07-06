# Typescript
Created: 06/07/2022 at 17:36
Tags: 
Related:

### Types
#### Basic
- undefined
- null
- boolean
- number
- string
- unknown
- any
- bigint
- symbol

##### Assignment
```typescript
let minutes: number
number = 2
```

#### Other
- array
- object
- function
- union
- enum

##### Assignment
Union
```typescript
let value: string | number | null = null
value = 12
value = 'cfc'
```

Array
```typescript
let arr2: string[]
arr2 = ['h', 'e']

let arr4: string[] | number[]
arr4 = ['hello', 234, 45.2, `intro`]
```

### Interface
```typescript
interface Student {
	name: string
	age?:  number //shorthand for age: number | undefined
	gender: 'male' | 'female' | 'other'
}
```

### Function
```typescript
function subtract (num1: number. num2: number): number { //: number is return type
	return num1 - num2
}
```