Solution :-

    var romanToInt = function(s) {
        let symbols = {
            I : 1,
            V : 5,
            X : 10,
            L : 50,
            C : 100,
            D : 500,
            M : 1000
        }
        let res = 0;

        for(let i=0; i<s.length; i++){
            const curr = symbols[s[i]];
            const next = symbols[s[i+1]];

            if(curr < next){
                res += next-curr;
                i++;
            }
            else{
                res += curr;
            }
        }

        return res;
    };

    Time complexity - O(N)
    Space complexity - O(N)

    Explanation -
    To solve this problem we will need to create a hash table in which the symbols present will have values assigned to them.

    We'll run a loop through the given string and check the current and the next character of the string simultaneously in the hashtable.

    If the value of the current character is smaller than the next character's value, then we'll subtract the current character's value from the next character's value. Once we do that, we can then add it to a result variable and also increase the index by 1 (We do this because when we meet for example I, and after it we see V, we understand that this is one number - IV. So we increase "i" by one such that it would skip the V (that's part of the quad)).

    If the value of the current character is greater than the next then we'll just simply add it to the result variable.

    After the loop ends, we just simply return the result.
