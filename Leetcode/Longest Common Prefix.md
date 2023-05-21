Solution :-

    var longestCommonPrefix = function(strs) {
        // return empty if input is empty
        if(!strs.length) return '';

        // looping through first string
        for(let i=0; i<=strs[0].length; i++){
            // looping through the other strings; starting j from 1 because we are already checking 1st string in line 10
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
