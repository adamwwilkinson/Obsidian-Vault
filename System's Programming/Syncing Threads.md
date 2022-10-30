Created: 2022-10-15 21:19
Tags:
Related: [[multi-threaded programming]]

### `mutexes`
If multiple threads update the same variables, the order in which they update is important.
Thread libraries support an abstraction called a `mutex` or *mutual exclusion*. Mutex variables are one of the primary means of providing syncing between threads.
The mutex variable acts like a *lock* protecting access to shared resources. One thread can lock a mutex variable at a time, and only they can unlock it.

#### Example
```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

int balance = 0;

pthread_mutex_t mutexbalance = PTHREAD_MUTEX_INITIALIZER;

void deposit(int amount)
{
    pthread_mutex_lock(&mutexbalance);
    {
        int currbalance = balance;      // read shared balance
        currbalance    += amount;
        balance         = currbalance;  // write shared balance
    }
    pthread_mutex_unlock(&mutexbalance);
}

void withdraw(int amount)
{
    pthread_mutex_lock(&mutexbalance);
    {
        int currbalance = balance;       // read shared balance
        if(currbalance >= amount) {
            currbalance -= amount;
            balance      = currbalance;  // write shared balance
        }
    }
    pthread_mutex_unlock(&mutexbalance);
}

    create threads...
....
    deposit(200);      // thread 1
    withdraw(100);     // thread 2
    deposit(500);      // thread 1
    withdraw(200);     // thread 3
```

### Race Conditions
When two threads attempt to modify the same variable at the same time, and the thread that does it last is the succusful one.

### Pthreads Functions to manage *mutexes*
#### Declaring Mutex Variables
- Statically: `pthread_mutex_t mymutex = PTHREAD_MUTEX_INITIALIZER;`
- Dynamically: `pthread_mutex_init();`

#### Locking and Unlocking
`pthread_mutex_lock()`, if mutex is already locked, call will block the calling thread until mutex is unlocked
`pthread_mutex_trylock()`, like the previous one but if the variable is already locked, returns an error code of `busy`
`pthread_mutex_unlock()`, will unlock if called by locking thread

#### Destroying
`pthread_mutex_destroy()`

### Condition Variables
Another way for threads to sync. Condition variabled allow threads to sync based upon the value of the data, rather the controlling thread access for the data like with mutexes.
Always used in conjunction with a mutex lock.

#### Example 
```c
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
#include <pthread.h>

#define MAX_ITEMS     10

pthread_cond_t cond_recv    = PTHREAD_COND_INITIALIZER;
pthread_cond_t cond_send    = PTHREAD_COND_INITIALIZER;

pthread_mutex_t cond_mutex  = PTHREAD_MUTEX_INITIALIZER;
pthread_mutex_t count_mutex = PTHREAD_MUTEX_INITIALIZER;

bool full=false;
int  count=0;

void *producer(void *thread_id)
{
    while(true) {
	pthread_mutex_lock(&cond_mutex);
        while(full) {
            pthread_cond_wait(&cond_recv, &cond_mutex) ;
        }

        pthread_mutex_unlock(&cond_mutex);
        pthread_mutex_lock(&count_mutex);

        ++count;
        full = true;
        printf("producer(%li):%i\n", pthread_self() , count);

        pthread_cond_broadcast(&cond_send);
        pthread_mutex_unlock(&count_mutex);

        if((count >= MAX_ITEMS) {
            break;
        }
    }
}

	

















void *consumer(void *thread_id)
{
    while(true) {
        pthread_mutex_lock(&cond_mutex);

        while(!full) {
            pthread_cond_wait(&cond_send , &cond_mutex) ;
        }

        pthread_mutex_unlock(&cond_mutex);
        pthread_mutex_lock(&count_mutex);

        --count;
        full = false;
        printf("consumer(%li):%i\n", pthread_self(), count);

        pthread_cond_broadcast(&cond_recv);
        pthread_mutex_unlock(&count_mutex);

        if((count >= MAX_ITEMS) {
            break;
        }
    }
}
```
### Pthreads Functions to manage *condition variables*
#### Declaring condition Variables
- Statically: `pthread_cond_t mycon = PTHREAD_COND_INITIALIZER;`
- Dynamically: `pthread_cond_init();`

#### Waiting and Signaling
`pthread_cond_wait()`, blocks the calling thread until condition is signalled
`pthread_cond_signal()`, used to signal another thread waiting on the condition variable
`pthread_cond_signal()`, used to signal several other threads waiting on the condition variable
`pthread_mutex_unlock()`, will unlock if called by locking thread

#### Destroying
`pthread_cond_destroy()`
