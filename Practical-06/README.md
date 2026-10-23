## Practical 6: Train Ticket Booking System Using Queue

### 1. Practical Title

Train Ticket Booking System Using Queue.

### 2. Problem Statement

Manage train ticket bookings using a queue. Confirm bookings while seats are available, place additional requests on a waiting list, and move the first waiting passenger to confirmed status when a confirmed ticket is cancelled.

### 3. Objective

* Understand queue operations and FIFO ordering.

* Maintain confirmed and waiting ticket lists.

* Apply enqueue, cancellation, and display operations to a booking scenario.

* Understand waiting-list promotion after cancellation.

### 4. Algorithm / Approach

1. Maintain a circular array for confirmed tickets and an array-based waiting list; each has a capacity of 5 in the supplied code.

2. **Book:** read a ticket number. If the confirmed queue is full, append the ticket to the waiting list if space is available; otherwise report that the waiting list is full. If a confirmed slot is available, enqueue the ticket.

3. **Cancel:** read the ticket number and search the confirmed circular queue.

   * If found, remove the ticket and shift subsequent queue entries as implemented in the program.

   * If the waiting list is non-empty, promote its first ticket to the confirmed queue and shift the waiting-list entries.

4. **Display:** print confirmed tickets and waiting-list tickets.

5. Repeat until Exit is selected.

*Implementation note: The supplied code uses fixed capacities and has a waiting-list shift/count update inside its loop that may not shift all entries correctly for a multi-person waiting list. This document describes the intended FIFO behaviour; verify the implementation before relying on multiple waiting-list promotions.*

### 5. Data Structure / Concept Used

* Circular queue for confirmed tickets

* Array-based FIFO waiting list

* `front` and `rear` pointers

* Queue search and removal

### 6. Test Cases

| Test Case | Input Scenario | Expected Result | 
| ----- | ----- | ----- | 
| **Seat available** | Book ticket 1001 | Ticket is confirmed | 
| **Confirmed queue full** | Book a sixth ticket while five are confirmed | Ticket goes to waiting list | 
| **Cancel existing ticket** | Cancel a confirmed ticket | Ticket is cancelled and first waiting ticket is promoted | 
| **Cancel absent ticket** | Cancel an unknown ticket number | Ticket not found | 
| **Empty confirmed queue** | Cancel when no confirmed tickets exist | No tickets | 

### 7. Sample Input and Output

Illustrative sequence: book tickets 101–105, book 106, then cancel 103.

```
Ticket booked
Ticket booked
Ticket booked
Ticket booked
Ticket booked
Added to waiting list
Enter ticket number to cancel: 103
Ticket cancelled
Waiting ticket 106 confirmed

```

### 8. Time Complexity

* **Booking:** $\mathcal{O}(1)$, excluding input/output.

* **Cancellation:** $\mathcal{O}(n)$ in the worst case because the confirmed queue is searched and elements may be shifted.

* **Display:** $\mathcal{O}(n + w)$, where $n$ is confirmed tickets and $w$ is waiting-list size.

### 9. Space Complexity

$\mathcal{O}(1)$ auxiliary space for the fixed arrays; total storage is $\mathcal{O}(\text{SIZE})$ for confirmed tickets and $\mathcal{O}(\text{SIZE})$ for waiting tickets.

### 10. Conclusion

Queues model the FIFO priority of ticket booking and waiting lists. Cancelling a confirmed ticket should release a seat for the earliest waiting passenger.
