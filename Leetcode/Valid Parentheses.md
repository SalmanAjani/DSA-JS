Solution (Using Stack) :-

    var isValid = function(s) {
        let stack = [];
        // Traverse each charater in input string
        for (let i = 0; i < s.length; i++) {
            // if open parentheses are present, push it to stack
            if (s[i] == '(') {
                stack.push(')');
            } else if (s[i] == '{') {
                stack.push('}');
            } else if (s[i] == '[') {
                stack.push(']');
            }
            // if a close bracket is found, check that it matches the last stored open bracket
            else if (stack.pop() !== s[i]) {
                return false;
            }
        }
        // if the stack is empty, all opening brackets have been matched with their corresponding closing brackets
        return stack.length === 0;
    };

    Time Complexity - O(N)
    Space Complexity - O(N)

    Explanation -
    The approach to solving this problem is pretty straightforward. Initially take an empty stack and everytime we encounter an open ended parentheses, we push the closed ended version of that parentheses into the stack.

    At the last step of the loop we will compare the value at the top of the stack with given string. If we find a pair of parentheses they are popped off from the stack. This will keep on going till the loop breaks.

    By the end, if there are no more elements left in the stack, that means every open ended bracket has found their corresponding closed ended bracket, so we simply return true.
