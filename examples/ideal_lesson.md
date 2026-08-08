# Ideal Lesson Example — Convolution

## 1. CRUX

Convolution applies a small matrix called a kernel to local regions of an image. At each location, corresponding values are multiplied and added. Different kernels can detect edges, blur images, sharpen images, or extract patterns.

## 2. PREREQUISITES

- Image as a matrix: pixels are represented by numbers.
- Element-wise multiplication and addition.

## 3. NEW CONCEPTS

- Kernel
- Convolution
- Stride
- Padding
- Feature map

## 4. CONCEPT: KERNEL

### Simple intuition

Imagine placing a small window over an image. The kernel is the question that the window asks about the pixels underneath it.

### Problem it solves

We want to detect local structure without manually inspecting every pixel.

### Formula

\[
Y(i,j)=\sum_m\sum_n X(i+m,j+n)K(m,n)
\]

### Symbols

| Symbol | Meaning |
|---|---|
| X | input image |
| K | kernel |
| Y | output |
| i,j | output location |
| m,n | kernel coordinates |

### Plain English

Multiply each kernel value by the corresponding image value, then add the products.

### Worked example

Input patch:

```text
1 2
4 5
```

Kernel:

```text
1  0
0 -1
```

Calculation:

```text
(1×1) + (2×0) + (4×0) + (5×-1)
= 1 + 0 + 0 - 5
= -4
```

### Connection to ML

Classical image processing often uses manually designed kernels. CNNs normally learn kernel weights from data.

```text
Classical CV
manual kernel
    ↓
local filtering

CNN
learned kernel
    ↓
feature extraction
```

### Common misconception

A kernel is not the entire algorithm. It is the set of weights used by the local operation.

### Practical use

- edge detection
- blur
- sharpening
- texture extraction
- CNN feature extraction

### Remember this

**A kernel is a small set of weights repeatedly applied to local regions of an image.**

## 5. HOW EVERYTHING CONNECTS

```text
Image
  ↓
Local patch
  ↓
Kernel
  ↓
Multiply + add
  ↓
Output feature map
```

## 6. MINI CHALLENGE

Given:

```text
Image patch:
2 3
4 5

Kernel:
1 -1
0  1
```

Calculate the output value.

Do not use a calculator.

## 7. CHECK MY UNDERSTANDING

1. What happens if every kernel value becomes twice as large?
2. Why can a kernel detect local patterns?
3. Why might a CNN learn kernels instead of manually designing them?
4. What would change if the stride increased?

## 8. KNOWLEDGE GRAPH

```text
Image
  ↓
Local patch
  ↓
Kernel
  ↓
Multiply + add
  ↓
Feature map
  ↓
CNN feature extraction
```

## 9. WHAT COMES NEXT?

The natural next concepts are stride, padding, output dimensions, and learned convolutional filters.
