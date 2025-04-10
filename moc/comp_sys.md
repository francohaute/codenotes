# Computer system 

## [Kernel](../topics/comp_sys/kernel.md)

- core component of an operating system
- bridge between application and hardware
-



## Memory

### Virtual memory

- What is virtual memory?
- What is the virtual adress space?

### Cache

- What is the purpose of the cache?





the hardware organization:
- The connections between the different parts of a computer system are made 
  through buses. A bus is a electrical conduct that carry fixed sized chunks 
  of information called words. The system of the word vary but modern computer
  use 64 bits or 8 bytes.
- I/O: Is what connects the system to the external world. Each IO device is connected 
  to the IO bus either through an adapter or controller.
- Main memory: temporary storage device that holds both the program and the data 
  that it manipulates while the processor executing the program. It consist of 
  a collection of DRAM chips 

A register is a small and fast storage location inside the cpu. It size varies 
depending on the cpu architecture.
There are different types of register that are meant to perform a specific task
like the program counter (PC) or the stack pointer.


the kernel as a collection of code and data structures that the system uses to 
manage processes.

Memory:
A machine level program sees memory as an array of bytes (chunks of 8 bits as the 
smallest adressable unit of memory) referred to as the virtual memory.

The size of the word determine the maximum size of the virtual adress space.((2^w)-1)






Concurrency: [article](https://wyounas.github.io/concurrency/2024/12/12/how-concurrency-works-a-visual-guide/)
A given sequence of states is a computation.
The representation of state space.
