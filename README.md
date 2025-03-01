# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Arrays, Linked Lists and Doubly Linked Lists all allow programmers to organize data in a sequence. So, how would you choose to use one over the other?

In your response, make sure to compare the time complexities for insertion, removal, and random access (grabbing a particular known element by index/position) for each data structure as well as memory usage and ease of traversal.

`Joshua`

### Response 1

I would choose an array if I need fast random access, working with contiguous memory, and have mostly static data or frequent access by index.

I would choose a singly linked list if I need frequent insertions/removals at the beginning or end and don't need backward traversal.

And I would choose a doubly linked list when I need to move in both directions and frequently add or remove things in the middle.

## Prompt 2

Imagine you are developing a web browser's "back" button functionality. When a user clicks "back," the browser should navigate to the previously visited webpage.

Would you use a stack or a queue to implement this functionality?

In your response, explain what a Stack/Queue is and why it would be best for this use case. Make sure that your response includes the terms LIFO or FIFO.

`Felipe`

### Response 2

To implement a back button in the browser, I would use a Stack data structure, which follows the Last In, First Out (LIFO) principle.

Every time a user navigates to a new page, we push the URL of the current page onto the stack. This allows us to track the user's browsing history. When the back button is clicked, we pop the current URL from the stack (removing the most recent page) and retrieve the previous URL, which becomes the new top of the stack.

By following this pattern, the user can navigate back through their history, as the stack always provides the last visited URL. The process continues until the user reaches the first visited page. This is because stacks operate in a LIFO manner, meaning the last element added is the first to be removed, which perfectly aligns with how the browser back button should function.

## Prompt 3

What is an Abstract Data Type and why are they worth learning about?

### Response 3

## Prompt 4

A few classic problems involving a stack are the `isBalanced` and `isPalindrome` functions. Choose one of these functions and provide a solution to it along with a brief lesson explaining how it works.
`Felipe`

### Response 4

```javascript
const isBalancedParentheses = (inputString) => {
  //  In order to have a balance parenthese we need a string with an even legth.
  if (inputString.length % 2 !== 0) return false;

  // we initialize a variable with a Stack as its value
  const stack = new Stack();
  // initialize an iterator
  let i = 0;
  // as long as the iterator is less than the length of the input string keep looping
  while (i < inputString.length) {
    // if input string [i] has a value of an opened parentheses push to stack
    if (inputString[i] === "(") {
      stack.push("(");
      // else pop from stack
    } else {
      stack.pop();
    }
    // increase iterator
    i++;
  }
  // if stack is empty return true else return false
  return stack.isEmpty();
};
```

The logic for this algorithm is that if a set of multiple parentheses is balanced then the number of open parentheses must match the number of closing parentheses, that's why at the end we check if the Stack is empty, because if it wasn't empty then it would mean that there is one or multiple matching sets of parentheses missing from my input, making the parentheses in the input unbalanced and that is why before making this check at the end of the function, we are first iterating though all the individual parentheses in the input and if a parentheses is open "`(`" the we are pushing that open parenthese in the stack and if it the parentheses is closed "`)`" then we are popping an element from our stack.
