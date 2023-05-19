Solution 1 (Brute Force) :-

    let res = [];
    for(let i=0; i<nums1.length; i++){
        for(let j=0; j<nums2.length; j++){
            if(nums1[i] === nums2[j]){
                res.push(nums2[j]);
            }
        }
    }
    return [...new Set(res)];
