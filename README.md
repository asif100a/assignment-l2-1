## What are some differences between interfaces and types in TypeScript?
## Ans:
Both interfaces and types used in TypeScript for defining data types. But there are some difference between interfaces and types:

- Interface can be extend types such as:
    ```bash
     interface Person {
        name: string;
     }

    interface Employee extends Person {
        id: number;
    } 
    ```
    On the other hand, types can't be extend types

- Interface can't directly define unions or tuples
    on the other hand, types can define unions or tuples type:
    ```bash
    type Status = "success" | "error";
    type Coordinates = [number, number];
    ```
- Based on performance Interface is slightly faster in TypeScript’s type-checking,
  Where Types may be with complex unions or intersections.


## Provide an example of using union and intersection types in TypeScript.
## Ans:
Here are two example of using union and intersection types in TypeScript:

**union**:
```bash
        type ID = string | number;

    function printID(id: ID) {
     if (typeof id === "string") {
        console.log("ID (string):", id.toUpperCase());
    } else {
        console.log("ID (number):", id.toFixed(2));
    }
    }
    ```

**intersection**:
```bash
       type Person = { name: string };
type Employee = { id: number; role: string };

type EmployeePerson = Person & Employee;

const alice: EmployeePerson = {
  name: "Alice",
  id: 123,
  role: "Developer"
};
    ```