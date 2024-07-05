# Toast: A Heterogeneous Memory Management System

## Abstract

Modern applications employ several heterogeneous memory types for improved performance, security, and reliability. To manage them, programmers must currently digress from the traditional load/store interface and rely on various custom libraries specific to each memory type, thus introducing programmability, performance, portability, and protection challenges.

To overcome these challenges, we propose **Toast**, a compiler-based approach that offers a simplified programming model based on the established load/store interface. Toast also includes programmable error-handling, memory consistency enforcement mechanisms, and a protection library for memory safety.

We have implemented Toast in the Clang/LLVM compiler framework, accompanied by a runtime library, employing software storage capabilities and hardware-based protection mechanisms. Our evaluation based on four applications that use heterogeneous memory types shows that Toast improves the programmability, portability, and protection of applications, while offering performance on par with a hand-optimized version of the application.

## Repository Structure

The Toast repository contains several submodules, each serving a distinct purpose in the overall system. Below is a detailed description of each submodule:

### [toast-llvm](./toast-llvm)

This submodule contains the modifications and extensions to the LLVM compiler framework necessary for Toast. It includes the compiler passes and transformations that enable the simplified programming model and programmable error-handling that Toast offers.

### [toast_runtime](./toast_runtime)

The `toast_runtime` submodule includes the runtime library for Toast. It supports the execution of applications using the Toast system, managing the interactions between the compiler-generated code and the underlying hardware and software protection mechanisms.

### [toast_erpc](./toast_erpc)

The `toast_erpc` submodule provides the implementation of `erpc` that Toast used for the performed experiments.

### [mpk-toast-protection](./mpk-toast-protection)

This submodule implements the hardware-assisted protection mechanism for Toast. It leverages Memory Protection Keys (MPK) to provide hardware-based protection for different memory regions. The primary goal is to ensure memory safety and prevent unauthorized access to sensitive memory areas.

### [toast-protection](./toast-protection)

The `toast-protection` submodule is the software-based protection library of Toast. It provides protection mechanisms and tools to ensure a comprehensive protection strategy for the various memory types and protection domains.
