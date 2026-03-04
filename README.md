# 🍦 Ice Cream Factory - OS Concurrency Project

A concurrent programming project demonstrating operating system concepts through simulation of an ice cream manufacturing plant. Implemented in both userspace (POSIX threads) and kernel space (Linux kernel module).

## 📋 Project Overview

This project simulates an ice cream factory where multiple customer orders are processed concurrently through a 6-stage production line with limited resources at each stage.

### Production Stages
| Stage | Resources | Time |
|-------|-----------|------|
| Boiling | 3 boilers | 2 sec |
| Sugar Addition | 2 machines | 1 sec |
| Flavor Addition | 2 machines | 1 sec |
| Coning | 2 stations | 1 sec |
| Freezing | 3 freezers | 2 sec |
| Wrapping | 2 stations | 1 sec |

## 🏗️ Architecture

The project has two implementations:

### 1. Userspace Version (`/userspace`)
- Uses POSIX threads (pthreads)
- Standard semaphores for synchronization
- Runs as a regular user process

### 2. Kernel Module Version (`/kernel`)
- Linux kernel threads (kthreads)
- Kernel-space semaphores
- System call interface
- Requires root privileges

## 🚀 Getting Started

### Prerequisites
- Linux operating system (Ubuntu recommended)
- GCC compiler
- Linux kernel headers (for kernel module)
- Root access (for kernel module)

### Building and Running

#### Userspace Version
```bash
cd userspace
gcc -pthread icecream_user.c -o icecream_user
./icecream_user
# Follow prompts to enter orders
