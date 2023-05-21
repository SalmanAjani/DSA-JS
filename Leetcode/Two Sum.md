Solution 1 (Nested Loops) :-

    var twoSum = function(nums, target) {
        for(let i=0; i<nums.length-1; i++){
            for(let j=i+1; j<nums.length; j++){
                if(nums[i]+nums[j] === target){
                    return [i,j];
                }
            }
        }
    };

Solution 2 (Efficient) :-

    var twoSum = function(nums, target) {
        const hashMap = new Map();

        for(let i=0; i<nums.length; i++){
            const currNum = nums[i];
            const numToFind = target-currNum;

            if(hashMap.has(numToFind)){
                return [hashMap.get(numToFind), i]
            }
            else{
                hashMap.set(currNum, i);
            }
        }
    };
