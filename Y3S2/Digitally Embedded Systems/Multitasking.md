Created: 05/10/2023 at 19:00

### Multitasking vs Multithreading
Multitasking means running several tasks in parallel.
Multithreading is a simpler and faster version of multitasking which switches between parallel threads.
If we have a single core processor, we can only have one thread running at a time, so we have to switch between them (time slicing).

### Task
- function/procedure with no params or return value
- often contains endless loop
- can read its own id
- can terminate itself and others

#### Scheduling
![[Multitasking-1696507365296.jpeg]]

#### Model
![[Multitasking-1696507419318.jpeg]]