# Ex6 Right Rotation LinkedList

## DATE: 17/11/2025
## AIM:
To write a Java  program to:
Create a singly linked list.
Rotate the linked list to the right by k positions.
Display the rotated linked list.

## Algorithm

1. Start the program.

2. Create a linked list node class containing data and next.

3. Insert elements into the linked list.

4. Count the number of nodes and make the list circular by connecting the last node to the head.

5. Find the new head by moving length - k steps forward and set the new tail's next to null.

6. Display the rotated linked list.

7. Stop the program.
   

## Program:
```
Developed by: Navinkumar V
RegisterNumber: 212223230141
```
```
import java.util.Scanner;

class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class RightRotateLinkedList {
    static Node rotateRight(Node head, int k) {
        if (head == null || k == 0) return head;
        Node temp = head;
        int length = 1;
        while (temp.next != null) {
            temp = temp.next;
            length++;
        }
        temp.next = head;
        k = k % length;
        int stepsToNewHead = length - k;
        Node newTail = temp;
        while (stepsToNewHead-- > 0) {
            newTail = newTail.next;
        }
        Node newHead = newTail.next;
        newTail.next = null;
        return newHead;
    }

    static void display(Node head) {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Node head = null, tail = null;
        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();
        System.out.println("Enter elements:");
        for (int i = 0; i < n; i++) {
            int val = sc.nextInt();
            Node newNode = new Node(val);
            if (head == null) {
                head = tail = newNode;
            } else {
                tail.next = newNode;
                tail = newNode;
            }
        }
        System.out.print("Enter k (positions to rotate): ");
        int k = sc.nextInt();
        head = rotateRight(head, k);
        System.out.println("Linked list after right rotation:");
        display(head);
        sc.close();
    }
}
```
## Output:

<img width="663" height="256" alt="image" src="https://github.com/user-attachments/assets/13124758-900f-497a-ad3f-ac1d4d9aeeb6" />


## Result:
Thus, the C program to perfom right rotation on linked list is implemented successfully.
