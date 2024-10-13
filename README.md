# Experiment-19
### Aim
The aim of this project is to study and implement a queue data structure using arrays. This involves understanding the fundamental operations of a queue—namely insertion, deletion, and display—while creating a simple menu-driven interface for user interaction.

### Theory
A **queue** is a linear data structure that follows the First In, First Out (FIFO) principle. This means that the first element added to the queue will be the first one to be removed. The main operations of a queue include:

1. **Insert (Enqueue)**: Add an element to the rear of the queue.
2. **Delete (Dequeue)**: Remove an element from the front of the queue.
3. **Display**: Show all elements currently in the queue.

### Algorithm for Queue Implementation Using STL

1. **Include Necessary Libraries:**
   - Include `<iostream>` for input and output operations.
   - Include `<queue>` for queue operations.

2. **Define the Main Function:**
   - Start the `main` function.

3. **Create a Queue:**
   - Declare a queue `q` of integers.

4. **Add Elements to the Queue:**
   - Use `q.push(30)` to add the element 30 to the queue.
   - Use `q.push(20)` to add the element 20 to the queue.
   - Use `q.push(10)` to add the element 10 to the queue.

5. **Access and Print the Front Element:**
   - Use `q.front()` to retrieve the front element of the queue (which should be 30).
   - Print the message "Front element before pop: " followed by the value retrieved from `q.front()`.

6. **Remove the Front Element:**
   - Use `q.pop()` to remove the front element from the queue.

7. **Print the New Front Element:**
   - Use `q.front()` to retrieve the new front element of the queue (which should be 20).
   - Print the message "Front element after pop: " followed by the value retrieved from `q.front()`.

8. **End the Program:**
   - Return 0 to indicate successful execution of the program.

### Code


```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;

    // Adding elements to the queue
    q.push(30);
    q.push(20);
    q.push(10);

    // Print the front element of the queue
    cout << "Front element before pop: " << q.front() << endl;

    // Remove the front element from the queue
    q.pop();

    // Print the front element after pop
    cout << "Front element after pop: " << q.front() << endl;

    return 0;
}
```
### Algorithm for Queue Implementation Using Array

1. **Define the Queue Class:**
   - Declare the `Queue` class with public members:
     - `int capacity` to hold the maximum size of the queue.
     - `int front` to track the index of the front element.
     - `int rear` to track the index of the last element.
     - `int* arr` to dynamically allocate memory for queue elements.

2. **Constructor:**
   - Initialize the queue with a specified capacity.
   - Allocate memory for `arr` with the given capacity.
   - Set `front` and `rear` to -1 to indicate that the queue is initially empty.

3. **Enqueue Method (push):**
   - Check if there is space in the queue (`rear + 1 < capacity`).
   - If the queue is empty (`front == -1`), set `front` to 0.
   - Increment `rear` and add the element at `arr[rear]`.
   - If the queue is full, print "Queue Overflow".

4. **Dequeue Method (pop):**
   - Check if the queue is empty (`front >= 0`).
   - If there is only one element (`front == rear`), reset `front` and `rear` to -1.
   - If there are multiple elements, increment `front`.
   - If the queue is empty, print "Queue Underflow".

5. **Peek Method:**
   - Check if the queue is empty (`front >= 0`).
   - If not empty, return the element at `arr[front]`.
   - If empty, return -1 to indicate that the queue is empty.

6. **Destructor:**
   - Deallocate memory used by `arr` when the queue object is destroyed.

7. **Main Function:**
   - Create an instance of `Queue` with a capacity of 5.
   - Enqueue three integers (10, 20, 30) onto the queue.
   - Call the `peek` method to print the front element.
   - Call the `pop` method to remove the front element.
   - Call the `peek` method again to print the new front element.

### Code



```cpp
#include <iostream>
using namespace std;

class Queue {
public:
    int capacity;
    int front;
    int rear;
    int* arr;

    // Constructor to initialize the queue
    Queue(int capacity) {
        this->capacity = capacity;
        arr = new int[capacity];
        front = -1; // Set front to -1 indicating an empty queue
        rear = -1;  // Set rear to -1 indicating an empty queue
    }

    // Enqueue: Add an element to the queue
    void push(int element) {
        if (rear + 1 < capacity) { // Check if there's space in the queue
            if (front == -1) { // If queue is empty
                front = 0;     // Initialize front
            }
            rear++;
            arr[rear] = element;
        } else {
            cout << "Queue Overflow" << endl;
        }
    }

    // Dequeue: Remove an element from the queue
    void pop() {
        if (front >= 0) {
            // If there's only one element, reset front and rear
            if (front == rear) {
                front = rear = -1; // Reset to indicate queue is empty
            } else {
                front++;
            }
        } else {
            cout << "Queue Underflow" << endl;
        }
    }

    // Peek: Get the front element of the queue
    int peek() {
        if (front >= 0) {
            return arr[front];
        } else {
            return -1; // Indicate that the queue is empty
        }
    }

    // Destructor to free allocated memory
    ~Queue() {
        delete[] arr;
    }
};

int main() {
    Queue q(5); // Initialize queue with a capacity of 5
    q.push(10);
    q.push(20);
    q.push(30);

    cout << "Front element: " << q.peek() << endl; // Should print 10

    q.pop(); // Remove 10
    cout << "Front element after pop: " << q.peek() << endl; // Should print 20

    return 0;
}
```
### Conclusion
In this project, we successfully implemented a queue using an array, allowing for basic operations such as insertion, deletion, and display through a menu-driven interface. Understanding the queue data structure is essential in various computing applications, including scheduling processes in operating systems, managing requests in web servers, and facilitating communication in asynchronous systems. This implementation reinforces the importance of data structures in programming and their practical applications in real-world scenarios.
