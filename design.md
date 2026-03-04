# Design Document - Ice Cream Factory

## Architecture Overview

### Userspace Implementation
- **Thread Model**: One thread per customer order + child threads per ice cream
- **Synchronization**: POSIX semaphores
- **Memory**: Process virtual memory
- **Scheduling**: OS scheduler

### Kernel Implementation  
- **Thread Model**: Kernel threads with manual wake-up
- **Synchronization**: Kernel semaphores
- **Memory**: Kernel space
- **Scheduling**: Kernel scheduler

## Synchronization Strategy

### Resource Semaphores
```c
boiler    // 3 resources
sugar     // 2 resources
flavor    // 2 resources
cone      // 2 resources
freezing  // 3 resources
wrapping  // 2 resources
