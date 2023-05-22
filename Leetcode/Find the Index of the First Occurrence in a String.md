Solution :-

    var strStr = function(haystack, needle) {
        let n = haystack.length;
        let m = needle.length;

        if(m===0){
            return 0; //empty needle
        }

        for(let i=0; i<=(n-m); i++){
            let flag = true;
            for(let j=0; j<m; j++){
                if(haystack[i+j] !== needle[j]){
                    flag = false;
                    break;
                }
            }
            if(flag){
                return i;
            }
        }
        return -1;
    };
