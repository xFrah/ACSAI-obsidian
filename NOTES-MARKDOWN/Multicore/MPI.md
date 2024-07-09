# Communicators
The communicators are a set of processes that can communicate with each other.
The default communicator is `MPI_COMM_WORLD`, which includes all the processes in the program. It is initialized by MPI_Init and finalized by MPI_Finalize.

# Sends and receives
## Send
- MPI_Send: Sends a message, it might either buffer the message and return or work in synchronous mode, which means that it will wait for the receiver to start receiving before returning. The decision is made by the MPI implementation. If there is enough buffer space, the message will be buffered, otherwise it will be synchronous.
- MPI_Bsend: It is a **buffered send**, it will always buffer the message and return immediately.
- MPI_Ssend: **Synchronous send**, it will wait for the receiver to start receiving before returning.
- MPI_Rsend: **Ready send**, it will return immediately, but the receiver must be ready to receive the message. It is programmer's responsibility to ensure that the receiver is ready.
- MPI_Isend: **Immediate send**, it will return immediately, but the message will be sent in the background. It is programmer's responsibility to ensure that the message is not modified until it is sent. In order to ensure that the message is sent, MPI_Wait must be called to check on the status of the message.

## Receive
- MPI_Recv: It doesn't return until a message is received. It looks for a message that matches its source, tag and communicator.
- MPI_Irecv: **Immediate receive**, it returns immediately, but the message will be received in the background. It is programmer's responsibility to ensure that the message is not modified until it is received. In order to ensure that the message is received, MPI_Wait must be called to check on the status of the message.

# Trapezoidal rule
The trapezoidal rule is a method to approximate the integral of a function. It divides the area under the curve into trapezoids and sums their areas.
So, very simply, the trapezoidal rule is:
1. Divide problem solution into subproblems
2. Solve subproblems
3. Combine subproblems to get the solution

# Collectives
- MPI_Bcast: Broadcasts a message from a process to the other processes in a communicator
- MPI_Gather: Gets data from all the processes in a communicator
- MPI_Allgather: Gets data from all the processes in a communicator, but the result is available to all processes
- MPI_Scatter: Divides data into parts and sends them across the proceesses
- MPI_Reduce: Performs a reduction operation on data from all processes
- MPI_Allreduce: Performs a reduction operation on data from all the processes, but the result is available to all processes
- MPI_Barrier: Blocks everything until all processes reach this point.
- MPI_Alltoall: It involves every process. Each send buffer of each process is divided into equal parts, then the parts are sent to all the processes.

# RMA (Remote Memory Access)
RMA is a way to access memory in another process, the other process doesn't need to do anything.

## Window
A window is a memory region that can be accessed by remote processes. It is created by MPI_Win_create and destroyed by MPI_Win_free.

### MPI_Win_create
It is a collective call, meaning that each process will expose its own buffer.
Or we can use MPI_Win_allocate to allocate memory for the window and expose it directly.

## Operations

- MPI_Put: Puts data from our buffer to the other process' buffer.
- MPI_Get: Gets data from the other process' buffer to our buffer.
- MPI_Accumulate: Accumulates data from our buffer to the other process' buffer. Like a sum, but it can be any operation.

## Synchronization
### Fence
A fence is a synchronization point. It is a way to ensure that all the operations are completed before continuing. We need to call MPI_Win_fence before starting the operations and MPI_Win_fence after finishing them. 

Fence commits all the changes. It is equal to MPI_barrier.

### MPI_Win_start
It is a way to start a group of RMA operations. It is a non-blocking call, so we can start the operations and continue with our work. The operations will be completed when we call MPI_Win_complete.

### Lock
It is a way to lock a window. It is useful when we want to ensure that no other process is accessing the window.