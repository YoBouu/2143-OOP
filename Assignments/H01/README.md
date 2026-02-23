# H01 - OOP Worksheet
**Name:** Hornel Cloubou
**Date:** Feb 23, 2026

## Part 1 — Stacks & Queues
* **Implementation:** Array-based stacks offer $O(1)$ access and are cache-friendly due to contiguous memory. Linked-lists avoid resizing overhead but have higher memory overhead per element.
* **Vector as a Queue:** Inefficient because `pop_front` (erasing index 0) requires shifting all subsequent elements, resulting in $O(n)$ time complexity.
* **Invariants:** * **Stack:** Last-In, First-Out (LIFO).
    * **Queue:** First-In, First-Out (FIFO).

## Part 2 — Overloading vs Overriding
| Feature | Overloading | Overriding |
| :--- | :--- | :--- |
| **Definition** | Same name, different parameters | Same name, same parameters |
| **Binding** | Static (Compile-time) | Dynamic (Runtime) |
| **Requirement** | Within same scope/class | Requires Inheritance |

## Part 3 — Constructors & Initialization Lists
In the `Widget` class, `const int id` **must** be initialized in the initialization list because constants cannot be assigned a value within the constructor body.
* **Correct Syntax:** `Widget(int val) : id(val) {}`

## Part 4 — Point2D Class
```cpp
#include <iostream>

class Point2D {
private:
    int x, y;
public:
    Point2D() : x(0), y(0) {}
    Point2D(int _x, int _y) : x(_x), y(_y) {}

    Point2D operator+(const Point2D& other) const {
        return Point2D(x + other.x, y + other.y);
    }

    bool operator==(const Point2D& other) const {
        return (x == other.x && y == other.y);
    }

    friend std::ostream& operator<<(std::ostream& os, const Point2D& p) {
        os << "(" << p.x << ", " << p.y << ")";
        return os;
    }
};
