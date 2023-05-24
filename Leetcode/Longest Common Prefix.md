Solution :-

    var longestCommonPrefix = function(strs) {

        // return empty if input is empty
        if(!strs.length) return '';

        // looping through first string
        for(let i=0; i<=strs[0].length; i++){

            // looping through the other strings
            // starting j from 1 because we are already taking 1st string in outer loop
            for(let j=1; j<strs.length; j++){

                // checking if the character is also present in the same position of each string
                if(strs[0][i] !== strs[j][i]){

                    // if not return the string up to and including the previous character
                    return strs[0].slice(0,i);
                }
            }
        }
        return strs[0];
    };

    Time Complexity - O(N^2)
    Space Complexity - O(1)

    Explanation -
    First we check if input is empty. If it is, we straight away return empty string as result.

    If it is not empty, we start by looping through the first string. The outer loop will iterate through the first string and the inner loop will iterate through the other strings. This is basically a way of checking if first string is a substring of other strings.

    If at any point we find a character in the first string that doesn’t match any of the character of the other strings, that means that the previous character tested marked the end of the longest prefix, so we return the first string up to and including that character.

    Lastly, if our loops make it all the way to the end, that means the entire first string was found in all other strings, and thus that the entire first string is the longest prefix.
