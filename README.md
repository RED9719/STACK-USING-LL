# STACK-USING-LL
class Stack:
    def __init__(self):
        self.stack = []

    def push(self, element):
        self.stack.append(element)
        print(f"Element {element} pushed onto the stack.")

    def pop(self):
        if not self.stack:
            print("Stack is empty! No element to pop.")
        else:
            popped_element = self.stack.pop()
            print(f"Element {popped_element} popped from the stack.")

    def display(self):
        if not self.stack:
            print("Stack is empty!")
        else:
            print("Stack elements from top to bottom:")
            for element in reversed(self.stack):
                print(element)

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
            element = input("Enter the element to push: ")
            stack.push(element)
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
