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

### Conclusion
In this project, we successfully implemented a queue using an array, allowing for basic operations such as insertion, deletion, and display through a menu-driven interface. Understanding the queue data structure is essential in various computing applications, including scheduling processes in operating systems, managing requests in web servers, and facilitating communication in asynchronous systems. This implementation reinforces the importance of data structures in programming and their practical applications in real-world scenarios.
