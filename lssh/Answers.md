## Multiple Choice and Short Answer Questions

Add your answers inline, below, with your pull request.

1. List all of the main states a process may be in at any point in time on a
   standard Unix system. Briefly explain what each of these states mean.

**Created/New State:**
    When a process is created, it occupies the created or new state. The process awaits admission to the "ready" state.
**Ready:**
    Ready state is when processes waiting in queue for the dispatcher to switch the processes waiting state into ready state for the CPU to execute. 
**Running:** 
    Once the processes waiting switches to ready, one of the CPU cores execute the process. It can be in either _kernel mode_ or _User mode_.
*Kernel Mode* 
    Kernel mode allows unrestricted access to hardware including execution of privileged instructions.
    Various instructions are privileged and can be executed only in kernel mode.
*User mode*
    When the application running user application, processes are in user mode can access their own instructions and data but not kernel instructions and data.
**Blocked**
    A process transitions to a blocked state when it cannot carry on without an external change in state or event occurring.
**Terminated**
    A process may be terminated, either from the "running" state by completing its execution or by explicitly being killed.

2. What is a Zombie Process? How does it get created? How does it get destroyed?
    On Unix, a zombie process or defunct process is a process that has completed execution but still has an entry in the process table: it is a process in the "Terminated state". This occurs for child processes, where the entry is still needed to allow the parent process to read its child's exit status: once the exit status is read via the wait system call, the zombie's entry is removed from the process table and it is said to be "reaped". A child process always first becomes a zombie before being removed from the resource table. In most cases, under normal system operation zombies are immediately waited on by their parent and then reaped by the system – processes that stay zombies for a long time are generally an error and cause a resource leak.

3. Describe the job of the Scheduler in the OS in general.
    It selects processes from the queue and loads them into memory for execution. Process loads into the memory for CPU scheduling. The primary objective of the job scheduler is to provide a balanced mix of jobs, such as I/O bound and processor bound. It also controls the degree of multiprogramming.
    
4. Describe the benefits of the MLFQ over a plain Round-Robin scheduler.
