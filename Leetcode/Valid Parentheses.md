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
        return !stack.length;
    };
