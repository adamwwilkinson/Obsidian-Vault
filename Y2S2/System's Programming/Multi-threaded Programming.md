Created: 2022-10-10 16:18
Tags: #topic/hardware 
Related: 

### What is a Thread
A sequence of instructions to be executed.
Has a set of *local variables* that belong to the thread, and a set of *shared global variables* that all threads can read and write.

#### Why
They allow us to deal with asynchronous events synchronously and efficiently, and they allow us to get parallel performance on a shared multiprocessor.

Threads are very useful when a process has multiple 'tasks' to perform independently of the others.

### Benefits
1. Responsiveness - one thread may provide rapid response while other threads are blocked or slow down
2. Resource sharing - by default threads share common code, data, and other resources, allowing multiple tasks to be performed simultaneously
3. Efficiency - creating and managing threads is much faster than performing the same tasks for processes
4. Scalability - a single threaded process can only run on one CPU no matter how many are available

![[Thread Drawing|900]]

### Threads vs Processes
Threads can be considered lightweight processes. Threads all share their process' resources, and they can be scheduled and executed independently.

### POSIX Threads
Initially, each process comprises a single, default thread. All other threads must be explicitly created by at run-time. 
`pthread_create()` creates a new thread and marks it as executable. It can be called any number of times from anywhere.

It accepts the arguments,
- thread: an opaque, unique identifier for a new thread
- attr: specify threads attributes, NULL for default values
- start_routine: the address of the C function that the thread will execute once created
- arg: a single argument that may be passed to `start_routine()`, passed as reference of 'pointer of type void' or NULL is no argument

```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

#define NUM_THREADS     5

void *hello_world(void *threadid)
{
  printf("Hello World, from thread #%li!\n", (long)threadid);
  pthread_exit(NULL);
}

int main(int argc, char *argv[])
{
  pthread_t threads[NUM_THREADS];

  for(long tid=0 ; tid < NUM_THREADS ; tid++) {
    printf("In main(): creating thread %li\n", tid);

    int err = pthread_create(&threads[tid], NULL, hello_world, (void *)tid);

    if(err != 0) {
      printf("ERROR; return code from pthread_create() is %d\n", err);
      exit(EXIT_FAILURE);
    }
  }

  pthread_exit(NULL);       // as main() is a thread, too
  return 0;
}
```

Once a program calls a thread, it's main becomes a thread, hence the exit at the end.

#### Passing More Arguments
```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

#define NUM_THREADS     5

struct thread_data{
   int  thread_id;
   int  sum;
   char *message;
};

struct thread_data thread_data_array[NUM_THREADS];

void *hello_world(void *threadarg)
{
   struct thread_data *my_data;
   ...
   my_data   = (struct thread_data *) threadarg;
   taskid    = my_data->thread_id;
   sum       = my_data->sum;
   hello_msg = my_data->message;
   ...
}

int main(int argc, char *argv[])
{
   ...
   for(long tid=0 ; tid < NUM_THREADS ; tid++) {
      thread_data_array[t].thread_id = t;
      thread_data_array[t].sum       = sum;
      thread_data_array[t].message   = messages[t];
      err = pthread_create(&threads[t], NULL, hello_world, (void *) &thread_data_array[t]);
      ...
   }
}
```

#### `pthread_join()`
```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

void *worker(void *threadarg)
{
    ....
    printf("thread #%li terminating.\n", (long)threadarg);
    pthread_exit((void*) threadarg);
}

int main(int argc, char *argv[])
{
    ....
    pthread_attr_t attr;

//  Initialize and set thread detached attribute
    pthread_attr_init(&attr);
    pthread_attr_setdetachstate(&attr, PTHREAD_CREATE_JOINABLE);  

    err = pthread_create(&thread[tid], &attr, worker, (void *)tid);
    ....

//  block main() until the worker() thread terminates
    err = pthread_join(thread[t], &status);
    ....

    printf("main() resumes execution\n");
    ....
}
```
