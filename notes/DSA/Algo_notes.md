# Complexity

## First points

- Input will always be greater than 0

- Functions do more work for more input

- Ignore constants, writing an progran for one or ten process in easy, but when considering about algorithms, we always need to think about the infinity.

- Ignore the base of logs and lower order terms.

### Complexity Types

- **Constant Time**
  - Indicated by 1 or *c*, which is constant independent of **n** i.e, input;

- **Log complexity**
  - If the operation includes division or multiplication by n, then it **log(n)** complexity.

    > Eg: trees

- **n complexity**
  - The time taken to complete a operation, for *n* no of inputs.
    > Lets says it takes 10 secs to count 10., Similarly it takes 100 seconds to count 100
- **n squared complexity**
  - The time taken to complete an operation, for *n* no of inputs.
    > Lets say it takes 100 seconds to count to 10, where the time is squared value of the input.

### [Big Oh notation](https://www.youtube.com/watch?v=vsgrJrphEHo&list=PLpPXw4zFa0uKKhaSz87IowJnOTzh9tiBk&index=3)

- **O(n)** is a complexity which is same or faster than with which we are comparing.
  - **o(n)** is a complexity which is faster than the one we are comparing to but not same.
- **θ(n)** is a complexity which is progressing at same rate as the one which we are comparing to.
- **Ω(n)** is a complexity which is same or slower than the one which we are comparing to.
  - **ω(n)** is a complexity which is slower, but not the same.
