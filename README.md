class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Stack:
    def __init__(self):
        self.head = None

    def is_empty(self):
        return self.head is None

    def push(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node
        print(f"Element {data} pushed onto the stack.")

    def pop(self):
        if self.is_empty():
            print("Stack is empty! No element to pop.")
            return None
        popped_node = self.head
        self.head = self.head.next
        print(f"Element {popped_node.data} popped from the stack.")
        return popped_node.data

    def display(self):
        if self.is_empty():
            print("Stack is empty!")
            return
        current = self.head
        print("Stack elements from top to bottom:")
        while current:
            print(current.data)
            current = current.next

def main():
    stack = Stack()
    while True:
        print("\nChoose an operation:")
        print("1. Push an element onto the stack")
        print("2. Pop an element from the stack")
        print("3. Display the stack")
        print("4. Exit")
        choice = input("Enter your choice (1/2/3/4): ")

        if choice == '1':
            data = input("Enter the element to push: ")
            stack.push(data)
        elif choice == '2':
            stack.pop()
        elif choice == '3':
            stack.display()
        elif choice == '4':
            print("Exiting...")
            break
        else:
            print("Invalid choice! Please enter 1, 2, 3, or 4.")
main()


