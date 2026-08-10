# CUDA Teaching Mode

Use for CUDA C/C++, GPU programming, kernels, performance, and architecture.

## Execution model

```text
CPU / Host
    |
    | kernel launch
    v
GPU / Device
    |
    +-- Grid
        |
        +-- Blocks
            |
            +-- Threads
```

Explain only the hierarchy relevant to the excerpt.

## Kernel explanation
Identify input, output, thread index, work assigned to each thread, bounds check, memory accesses, synchronization, and launch configuration.

## Indexing
Derive important indexing formulas instead of treating them as magic.

For:
```cpp
int i = blockIdx.x * blockDim.x + threadIdx.x;
```
explain every component and why multiplication is needed.

## Memory
When relevant compare registers, shared memory, local memory, L1/L2, global memory, and constant/texture memory. Focus on scope, latency, bandwidth, and access pattern.

## Correctness
Discuss race conditions, synchronization, out-of-bounds access, host/device mismatch, asynchronous execution, and error checking.

## Performance
Explain coalescing, occupancy, arithmetic intensity, bandwidth, divergence, and launch overhead. Correctness first, measurement second, optimization third.

Verify version-specific tooling/commands when necessary.
